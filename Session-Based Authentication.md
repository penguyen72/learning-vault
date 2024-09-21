#Authentication

Relies on a server-side mechanism that creates and stores a unique identifier for each user session.
### Workflow
1. When a user logs in, the server generates a session ID and sends it to the client as a cookie
2. The client then sends the cookie back with every request
3. The server validates it against its session store

##### Note: The server keeps track of the user's state and permissions

### Drawbacks
- Consumes a lot of server resources
- Scalability issues
- Exposes security risk if the cookies are not encrypted or protected

