Algorithm
1. Create adjacency list
2. Get all in degrees for each node
3. Add nodes with zero in degrees to a queue
4. loop through the queue
	1. for each popped node remove an in degree from its child and add the child to the queue if its in degrees is 0
5. a cycle if detected if not all nodes were popped