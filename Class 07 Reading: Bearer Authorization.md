
# ***Read: Class 07 - Bearer Authorization***

***

## **JSON Web Token:**

    It is an open standard (RFC 7519) that defines a compact and self-contained way for securely transmitting information between parties as a JSON object. JWTs can be signed using a secret (with the HMAC algorithm) or a public/private key pair using RSA or ECDSA.

***

## **When should you use JSON Web Tokens?**

- Authorization:

       This is the most common scenario for using JWT. Once the user is logged in, each subsequent request will include the JWT, allowing the user to access routes, services, and resources that are permitted with that token. Single Sign On is a feature that widely uses JWT nowadays, because of its small overhead and its ability to be easily used across different domains.

- Information Exchange:

        JSON Web Tokens are a good way of securely transmitting information between parties. Because JWTs can be signed—for example, using public/private key pairs—you can be sure the senders are who they say they are. Additionally, as the signature is calculated using the header and the payload, you can also verify that the content hasn't been tampered with.

***

## **What is the JSON Web Token structure?**

In its compact form, JSON Web Tokens consist of three parts separated by dots (.), which are:

- Header
- Payload
- Signature

        Therefore, a JWT typically looks like the following.

        xxxxx.yyyyy.zzzzz

### **Header:**

    The header typically consists of two parts: the type of the token, which is JWT, and the signing algorithm being used, such as HMAC SHA256 or RSA.

For example:

    {
        "alg": "HS256",
        "typ": "JWT"
    }

### **Payload:**

    he second part of the token is the payload, which contains the claims. Claims are statements about an entity (typically, the user) and additional data. There are three types of claims: registered, public, and private claims.

- Registered claims:

        These are a set of predefined claims which are not mandatory but recommended, to provide a set of useful, interoperable claims. Some of them are: iss (issuer), exp (expiration time), sub (subject), aud (audience), and others.

- Public claims:

        These can be defined at will by those using JWTs. But to avoid collisions they should be defined in the IANA JSON Web Token Registry or be defined as a URI that contains a collision resistant namespace.

- Private claims:

        These are the custom claims created to share information between parties that agree on using them and are neither registered or public claims.

For example:

    {
        "sub": "1234567890",
        "name": "John Doe",
        "admin": true
    }

### **Signature:**

    To create the signature part you have to take the encoded header, the encoded payload, a secret, the algorithm specified in the header, and sign that.

For example:

    HMACSHA256(
    base64UrlEncode(header) + "." +
    base64UrlEncode(payload),
    secret)    

***

## **Putting all together:**

The output is three Base64-URL strings separated by dots that can be easily passed in HTML and HTTP environments, while being more compact when compared to XML-based standards such as SAML.

The following shows a JWT that has the previous header and payload encoded, and it is signed with a secret.

![](./Class-07%20images/legacy-app-auth-5.png)


## **Why should we use JSON Web Tokens?**

The benefits of JSON Web Tokens (JWT) when compared to Simple Web Tokens (SWT) and Security Assertion Markup Language Tokens (SAML): 

- As JSON is less verbose than XML:

        When it is encoded its size is also smaller, making JWT more compact than SAML. This makes JWT a good choice to be passed in HTML and HTTP environments.

- Security-wise, SWT can only be symmetrically signed by a shared secret using the HMAC algorithm:

        However, JWT and SAML tokens can use a public/private key pair in the form of a X.509 certificate for signing. Signing XML with XML Digital Signature without introducing obscure security holes is very difficult when compared to the simplicity of signing JSON.

- JSON parsers are common in most programming languages:

        because they map directly to objects. Conversely, XML doesn't have a natural document-to-object mapping. This makes it easier to work with JWT than SAML assertions.

- Regarding usage, JWT is used at Internet scale:

        This highlights the ease of client-side processing of the JSON Web token on multiple platforms, especially mobile.

***

[README](README.md)
