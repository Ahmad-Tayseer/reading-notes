
# ***Read: Class 06 - Authentication***

***

## **Authentication:**

    - Cryptographic hash algorithms MD5, SHA1, SHA256, SHA512, SHA-3 are general purpose hash functions, designed to calculate a digest of huge amounts of data in as short a time as possible.

    - Many desktop applications and almost every web service need to store a collection of user data and the passwords, that has to be stored using a hashing algorithm.

    - Hashing is the greatest way for protecting passwords and considered to be pretty safe for ensuring the integrity of data or password.

***

## **Problems With Cryptographic Hash Algorithm:**

- Brute Force attack.

        Hashes can't be reversed >> An attacker can simply keep trying different inputs until he does not find the right now that generates the same hash value.

- Hash Collision attack.

        Hash functions have infinite input length and a predefined output length >> There is inevitably going to be the possibility of two different inputs that produce the same output hash.

***

## **What exactly could be a good for securing your passwords with hashing?**

- PBKDF2.
- BCrypt.

***

## **Basic Access Authentication:**

    Basic access authentication is a method for an HTTP user agent (e.g. a web browser) to provide a user name and password when making a request.

***

## **Features:**

    HTTP Basic authentication (BA) implementation is the simplest technique for enforcing access controls to web resources because it does not require cookies, session identifiers, or login pages; rather, HTTP Basic authentication uses standard fields in the HTTP header.

***

## **Security:**

    The BA mechanism does not provide confidentiality protection for the transmitted credentials. They are merely encoded with Base64 in transit and not encrypted or hashed in any way. Therefore, basic authentication is typically used in conjunction with HTTPS to provide confidentiality.

***

## **Security:**

- Server side:

        WWW-Authenticate: Basic realm="User Visible Realm"

-  The server may choose to include the charset parameter:

        WWW-Authenticate: Basic realm="User Visible Realm", charset="UTF-8"

- Client side:

        username:password

        Or QWxhZGRpbjpvcGVuIHNlc2FtZQ== >> Authorization: Basic QWxhZGRpbjpvcGVuIHNlc2FtZQ==

***

[README](README.md)
