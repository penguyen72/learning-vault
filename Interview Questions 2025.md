## Meta
#### Phone 1:
Given a binary tree. Return the total sum of all root-to-leaf numbers. A root-to-leaf number is a path that represents the number where 1 -> 2 -> 3 would represent 123

#### Phone 2:
Given two intervals, return a single array where the intervals are merged together
## Google
#### Phone 1:
Given a dictionary of words, implement a function where when given an input will return the words that start with that input. For example, `words = {'google', 'facebook', 'googling'}` and `input = 'goog'` should return `['google', 'googling']`.

Follow up: 
Instead of receiving an input that can be a multiple characters, how would you adjust your code to make it more similar to a user typing on a keyboard. The input will instead be keystrokes and spaces indicate the end of the current word.

#### Onsite 1:
You have a backend service that pings your service at certain intervals the number of users there are in that second. You want to calculate the moving average of the the last k pings. 

Follow up:
Implement a function that will return the average where the top x values are not considered in the average.

#### Onsite 2:
Given an array, return the most frequent element.

Follow up:
Implement a function that returns the top k frequent elements

#### Onsite 3:
You are given an array of logs with the following structure
```
struct Log {
	source_id: string
	data: string
}
```

The logs that you are given could be extremely large. Implement a function where when given a integer,`x` , the function should return the array of logs truncated to `x` such that the each log source is fairly distributed
## Snowflake
#### Phone 1:


#### Phone 2:


## Databricks
#### Phone 1:
Given a string `s` and a string `t`, find the first occurrence of the string `t` in `s` where the substring can be any permutation of the string `t`
## Anduril
#### Phone 1:
Implement a multi part file upload service. There should be three functions: 
`upload_file(fileId, partIndex, data)`
- This function will upload a file for a particular index with some data

`complete_upload(fileId)`
- This function will be called only when a file has finished uploading by the client. If there are any missing parts, return an error. If there are no missing parts, then return the data of the entire file.

`get_bytes_at_range(fileId, start, end)`. 
## Vercel
## Snapchat
## Scale
## Coinbase
## Waymo



