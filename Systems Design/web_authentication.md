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

<img width="934" height="452" alt="hmac_01" src="https://github.com/user-attachments/assets/4f71899d-5408-40ce-96c4-afbe77208b9e" />


**HMAC** is a **symmetric** signing method the same secret key is used to sign and verify the token. This is simpler and more efficient, but it requires sharing the secret key with any service that needs to verify the token, which can be a security concern.

**RSA** and **ECDSA**, on the other hand, are **asymmetric** signing methods, they use a private key to sign the token and a public key to verify it. This allows for a more secure architecture where private key is kept secret and only used for signing, while any service can verify the token using the public key.

This adds some complexity and computational overhead compared to HMAC.

<img width="972" height="432" alt="image" src="https://github.com/user-attachments/assets/cabceb1e-b17a-4df1-a894-dc74c574f8d1" />

_**The choice of signing algorithm depends on your security requirements and system architeture**_. If you have a monolithic application or trust all the services in your system, HMAC might be sufficient. But if you have a microservice architecture or need to share JWTs with untrusted third-party services, RSA or ECDSA provide a more secure solution.

<img width="734" height="378" alt="monolithic_and_microservice" src="https://github.com/user-attachments/assets/488faa9a-f950-4ca7-a882-ae7efa59c4d3" />

One challenge with JWTs is handling token expiration. If a token is stole, it can be used until it expires.

To mitigate this, you can use refresh tokens in combination with short-lived access tokens. The access token is the actual JWT used for authentication on each request. It has a short expiration time, typically around 15 minutes. The refresh token, on the other hand, has a much longer expiration time perhaps several days or weeks.

<img width="336" height="273" alt="token_expiration_01" src="https://github.com/user-attachments/assets/15940b6d-978e-4afa-9897-34141df51083" />

<img width="356" height="223" alt="token_expiration_02" src="https://github.com/user-attachments/assets/277ac96e-996b-4d25-9c98-b4c406a1ac40" />

<img width="356" height="223" alt="token_expiration_03" src="https://github.com/user-attachments/assets/42e9ef13-4750-48ba-89d6-891bdbf848e7" />

When the access token expires, instead of requiring the user to log in again, the client can send the refresh token to a special token endpoint on the server. The server checks if the refresh token is valid and hasn't been revoke. if everything checks out, the server issues a new access token.

<img width="753" height="336" alt="refresh_token" src="https://github.com/user-attachments/assets/f49c77c0-4569-4154-b201-87ce540e4ae6" />

This process happens behind the scenes, without requiring interaction from the user.

This approach strikes a balance between security and user experience. The short-lived access tokens limit the window of potential misuse if a token is stolen while the long-live refresh tokens allow users to remain authenticate for a extended period without needing to log in repeatedly. 

<img width="421" height="310" alt="security_user_experience" src="https://github.com/user-attachments/assets/142e1e15-9d21-498f-8011-9efacf0d3e38" />

It's important to note that refresh token is only sent when the access token has expired, not on every request.

<img width="388" height="228" alt="refresh_token_01" src="https://github.com/user-attachments/assets/114fd1b0-1e5a-46bc-9f69-d8c66082ea5f" />

The access token is sent on every request that requires authentication.

<img width="388" height="228" alt="refresh_token_02" src="https://github.com/user-attachments/assets/0473539c-9c99-465a-8c03-cc182969f81a" />

So when should I used session-based authentication, and when are JWTs a better choice?

Session-based authentication is a good fit when you need the ability to revoke sessions instantly. If a user reports theis account as compromised, you can immediately invalidate their session on the server side.

Sessions are also a good choice if you already have a centralized data store for other purposes. In this case, you can leverage that existing infrastructure for session storage as well.

<img width="936" height="208" alt="when_to_use_session_vs_jat_authentication" src="https://github.com/user-attachments/assets/baf52ad2-b528-49ed-b843-15d2f229ef42" />

However, it's important to keep in mind that using centralized session store does add some latency to each request, as the server needs to fetch the session data from the store. Finally, sessions keep sensitive data on the server, which can be a security advantage.

<img width="393" height="314" alt="session_latency" src="https://github.com/user-attachments/assets/cb96472d-4555-4d7b-8e35-6aeb55e3ffc1" />

On the other hand, JWTs are a great choice when you need a stateless architecture. Because JWTs store all the necessary data in the token itself, your server doesn't need to keep track of sessions in memory or in a database.

This makes it much easier to scale your application horizontally across multiple servers.

JWTs are also useful when you need to share authentication data with other services. For instance, in a microservice architecture a JWT generated by the authentication service can be verified and trusted by other services without needing to contact the authentication service on each request.

<img width="596" height="395" alt="share_authentication" src="https://github.com/user-attachments/assets/56be1162-b27a-4752-b518-c711e56a8714" />

If you do choose JWTs, consider implementing refresh tokens to balance security and user experience.
