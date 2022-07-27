# Install With Docker

You can also install `Ktra` with the [Docker](https://www.docker.com/) image.  

```
docker pull ghcr.io/moriturus/ktra:latest
```

Or, if you want to pull a fixed version image, try this.  

```
docker pull ghcr.io/moriturus/ktra:0.7.0
```

> ***Note***:  
> The latest published `Ktra` version is [![ktra at crates.io](https://img.shields.io/crates/v/ktra.svg)](https://crates.io/crates/ktra).

---

### Tags

There are several images tagged with features and releases.  
Any commit on `develop` branch builds images listed below:

- `latest`
    - `db-sled` featured image.
- `openid-latest`
    - `db-sled` featured image.
    - `openid` support for user authentication and authorization
- `db-redis-latest`
    - `db-redis` featured image.
- `db-redis-openid-latest`
    - `db-redis` featured image.
    - `openid` support for user authentication and authorization
- `db-mongo-latest`
    - `db-mongo` featured image.
- `db-mongo-openid-latest`
    - `db-mongo` featured image.
    - `openid` support for user authentication and authorization


Similarly, images below are built automatically when tags are pushed:

- `{VERSION}` *(e.g. `0.7.0`)*
    - `db-sled` featured image.
- `openid-{VERSION}`
    - `db-sled` featured image.
    - `openid` support for user authentication and authorization
- `db-redis-{VERSION}`
    - `db-redis` featured image.
- `db-redis-openid-{VERSION}`
    - `db-redis` featured image.
    - `openid` support for user authentication and authorization
- `db-mongo-{VERSION}`
    - `db-mongo` featured image.
- `db-mongo-openid-{VERSION}`
    - `db-mongo` featured image.
    - `openid` support for user authentication and authorization

> ***Note***:  
> The openid images are only available starting with `0.7` version


---

### Registry

All of the docker images are built with [emk/rust-musl-builder](https://github.com/emk/rust-musl-builder) image and stored at [GitHub Container Registry](https://docs.github.com/en/free-pro-team@latest/packages/getting-started-with-github-container-registry/about-github-container-registry).  
These are public images so you can pull them without any authentication.
