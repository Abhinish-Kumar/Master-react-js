# JWT

1. - Public , Private cryptography :- its a security  mechanism , it generates two keys public keys and private keys.
- You can give this public key to any one , it incripts user data, but no one can decrypt it . Only you can use this private key to decrypt the user data.


2. Stateless,statefull:- In state less we dont keep data on data base, state full is the state where we store the data of state in database or in another file on server.
3. Whoever has token can access this site. 



## What is JWT?

JSON WEB TOKEN :- made with three components. (a long string).

==> JSON Web Tokens are an open, industry standard RFC 7519 method for representing claims securely between two parties.

==> JWT.IO allows you to decode, verify and generate JWT.

keys to unlock access


JWT takes data enrypt it , by encryption algorithm (HS256)

<img src="/image/JWT1.png" />

Encoded code looks like :- `eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c`

divided into 3 parts

1. Red define which algorithm are you using.
2. Purple define your information.
3. Blue is your signature.


Decoded data

1. Header :- define algorithm type
2. Payload data :- any information (id,iat(issue date)).
3. Verif Signature :-your-256-bit-secre ; it generate your secret key. used to generate signature. (key)





## Authentication Authorization


Authentication :- Prove that its you
Authorized :- You have authority to use this feature


These are the best use of JWT



## How to store JWT token to clent browser securely.

1. store JWT token to localStorage
2. in session Storage
3. Cookies(more secure)


Best way is to expire the key. (refresh token mechanism)


## Flow 

Client request to the server with login detail , server give a token to the client, every time your request took token with itself.

1. access token
2. refresh toke (to renew your access token when it expires)(stateful)


## JWT vs sessions

1. client
2. server
3. database


### How we use stateless mechanism. 

Client send login detail to server server check user in database and then issue a JWT Token to the client from server. 
And when client send a token to the server , we directly velidate the token to the server without database interaction, because its stateless, and we have public private mechanism. 

Why :- refresh token facility, not interaction with database thats why its fast.

### Session

Statefull


Client send login detail to server, validate with database, send ckkoie session id, to store in browser, same session id is already stored in our database.Always DB call. Slow.



















