# Features

`Ktra` has now features listed below.

- Almost pure Rust.
- Minimum [Alternate Registry](https://doc.rust-lang.org/cargo/reference/registries.html) implementation.
- Secure user management with [Argon2](https://en.wikipedia.org/wiki/Argon2) or as an OpenID Service
  Provider (compatible with `.well-known` discoverable identity providers such as gitlab)
- [Sled](https://github.com/spacejam/sled) as its internal database.
    - via `db-sled` feature turned on by ***default***.
- [Redis](https://redis.io/) support.
    - via `db-redis` feature.
- [MongoDB](https://www.mongodb.com/) support.
    - via `db-mongo` feature.
