#Authentication 

JWT is short for JSON Web Token

The token contains three parts:
- **Header** - Specifies the signing algorithm and creates the digital signature
- **Payload** - Defines token expiration and makes the authentication request
- **Signature** - Verifies message data

##### Note: the token is encoded NOT encrypted
### How is it secure?
- The signature is used to validate that the token has not been tempered with or modified
- The signature is created by hashing the header and payload with a secret known to the server
- If the payload has been tempered with, then the signature produced when validating the token will be incorrect
>This
>is

```json
// JWT Token Signature
HMACSHA256(
	base64UrlEncode(header) + '.' +
	base64UrlEncode(payload),
	secret
)
```