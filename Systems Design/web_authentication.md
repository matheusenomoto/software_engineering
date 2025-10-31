# Web Authentication

**Reference:** [ByteByteGo](https://www.youtube.com/watch?v=fyTxwIa-1U0)

## Session vs. JWT


<img width="961" height="264" alt="session_based_authentication" src="https://github.com/user-attachments/assets/51f900e1-20ca-4a33-8245-e8abd3b8cb5c" />

<img width="962" height="264" alt="jwt_based_authentication" src="https://github.com/user-attachments/assets/6a78c797-7376-4ac5-98f8-8fefb426cab3" />

## Signing JWTs algorithms

<img width="98" height="98" alt="jwt" src="https://github.com/user-attachments/assets/b010ea77-9e3c-4d00-bb9e-4e81d9fc15a9" />

* HMAC
* RCA
* ECDSA

**PLACEHOLDER IMAGE**

**HMAC** is a **symmetric** signing method the same secret key is used to sign and verify the token. This is simpler and more efficient, but it requires sharing the secret key with any service that needs to verify the token, which can be a security concern.

**RSA** and **ECDSA**, on the other hand, are **asymmetric** signing methods, they use a private key to sign the token and a public key to verify it. This allows for a more secure architecture where private key is kept secret and only used for signing, while any service can verify the token using the public key.

This adds some complexity and computational overhead compared to HMAC.
