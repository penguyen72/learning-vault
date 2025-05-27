### How to use Next.js effectively
Based on research, it seems like the most effective way to use Next.js properly is to use it alongside Tanstack Query

Although it is possible to create an application without Tanstack Query, it seems like when scaling application to support LARGE amounts of data where your database size is more than a million. 

The queries often get fairly slow, so it is important to isolate your components to properly Suspense the component until the data has loaded. It is not ideal to load the data at the root level of the app since this will cause the initial load time of the page to be long. 

You want to query the database in the component itself. However, this creates a weird pattern where the server component needs to be created as a wrapper to stream data into the client component. Assuming you want your data to be stateful. 

**NOTE:** if the data does not need to be stateful, then this might not be needed

To improve this, you can prefetch the query at the root of the page and simply hydrate the data to the client components

```tsx
// app/posts/page.jsx
import {
  dehydrate,
  HydrationBoundary,
  QueryClient,
} from '@tanstack/react-query'
import Posts from './posts'

export default async function PostsPage() {
  const queryClient = new QueryClient()

  await queryClient.prefetchQuery({
    queryKey: ['posts'],
    queryFn: getPosts,
  })

  return (
    // Neat! Serialization is now as easy as passing props.
    // HydrationBoundary is a Client Component, so hydration will happen there.
    <HydrationBoundary state={dehydrate(queryClient)}>
      <Posts />
    </HydrationBoundary>
  )
}
```

The client component will then grab the data from cache and without needing to refetch it again.

```tsx
// app/posts/posts.jsx
'use client'

export default function Posts() {
  // This useQuery could just as well happen in some deeper
  // child to <Posts>, data will be available immediately either way
  const { data } = useQuery({
    queryKey: ['posts'],
    queryFn: () => getPosts(),
  })

  // This query was not prefetched on the server and will not start
  // fetching until on the client, both patterns are fine to mix.
  const { data: commentsData } = useQuery({
    queryKey: ['posts-comments'],
    queryFn: getComments,
  })

  // ...
}
```

#### Research
`useQuery` will cause all queries to suspend until the first one is finished. Streaming does not work properly. In order to work around this, `@tanstack/react-query` states that you should use `useSuspenseQuery`. 

**DO NOT** use server actions for anything other than form submission. When querying data, simply use server components and stream data in. This is good for static and non stateful data. It is also good for eliminating component nesting when you have a component that you want to be stateful.