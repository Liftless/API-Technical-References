JSON Web Token (JWT) - Reference
--------------------------------

[RFC7519](https://datatracker.ietf.org/doc/html/rfc7519) JSON Web Token (JWT)

# Body

```json
{
  "iss": /* Issuer       */ "liftless-relay-api",
  "sub": /* Subject      */ ( user.id ),
  "aud": /* Audience     */ [ "http://api.liftlessrelay.com" ],
  "exp": /* Expiration   */ ( Math.round(Date.now() / 1000) + TOKEN_LIFETIME_SECONDS ),
  "nbf": /* Not Before   */ ( Math.round(Date.now() / 1000) + TOKEN_DELAY_SECONDS ),
  "iat": /* Issued At    */ ( Math.round(Date.now() / 1000) ),
  "jti": /* JWT ID       */ ( crypto.randomBytes(16).toString('hex') ),
  "typ": /* Type         */ "application/jwt",
  "cty": /* Content Type */ "JWT",
}
```

- [`iss`](https://datatracker.ietf.org/doc/html/rfc7519#section-4.1.1): (Issuer) Claim. Who issued the JWT.
- [`sub`](https://datatracker.ietf.org/doc/html/rfc7519#section-4.1.2): (Subject) Claim. Who this JWT is for.
- [`aud`](https://datatracker.ietf.org/doc/html/rfc7519#section-4.1.3): (Audience) Claim. Who this JWT can be presented to.
- [`exp`](https://datatracker.ietf.org/doc/html/rfc7519#section-4.1.4): (Expiration Time) Claim. When this token is no longer valid.
- [`nbf`](https://datatracker.ietf.org/doc/html/rfc7519#section-4.1.5): (Not Before) Claim. When this token is not valid until.
- [`iat`](https://datatracker.ietf.org/doc/html/rfc7519#section-4.1.6): (Issued At) Claim. When this JWT was created.
- [`jti`](https://datatracker.ietf.org/doc/html/rfc7519#section-4.1.7): (JWT ID) Claim. The ID of this JWT.
- [`typ`](https://datatracker.ietf.org/doc/html/rfc7519#section-5.1): (Type) Header Parameter. Indicates this is a JWT.
- [`cty`](https://datatracker.ietf.org/doc/html/rfc7519#section-5.2): (Content Type) Header Parameter. Indicates if there is a nested JWT.

## Types

Found in [RFC7519 2. Terminology](https://datatracker.ietf.org/doc/html/rfc7519#section-2)

- `StringOrURI`

If it contains a colon (`:`) then it must be a URI.
Otherwise, any string.

- `NumericDate`

Seconds since epoch 1970-01-01T00:00:00Z UTC. Does not need to be a whole integer.

In Node.js, this code may be used: `const wholeSecondsSinceEpoch = Math.round(Date.now() / 1000);`

<!-- END -->