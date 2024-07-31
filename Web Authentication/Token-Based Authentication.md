#Authentication 

Relies on a client-side mechanism that uses self-contained tokens to store and transmit user information.
### Workflow
1. The client sends a request to the server with their credentials, which issues an access request to the server or protected resource
2. The server validates the credentials
3. The server generates a secure, signed authentication token (usually a [[JWT Token]]) for the user for a specific period of time
4. The token is transmitted back to the user's browser, which stores it. 
5. The token is sent the token with every request, and the server verifies it by checking its signature and validity.
6. The token is destroyed once the user logs out or closes the server
##### Note: The server does not need to keep track of any state 

### Drawbacks
- It is difficult to invalidate the token from the server
- If poorly configured, it can lead to widespread breaches
- Requires constant revalidation
