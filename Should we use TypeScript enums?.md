### POJO Approach
```tsx
const LOG_LEVEL = {
	DEBUG: 'Debug',
	WARNING: 'Warning',
	ERROR: 'Error'
} as const

type ObjectValue<T> = T[keyof T]
type LogLevel = ObjectValue<typeof LOG_LEVEL>
```

References:
- [Article](https://lumin8media.com/blog/should-we-use-typescript-enums)
- [Youtube](https://www.youtube.com/watch?v=jjMbPt_H3RQ)
