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



















