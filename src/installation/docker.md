# Install With Docker

You can also install `Ktra` with the [Docker](https://www.docker.com/) image.  

```
docker pull ghcr.io/moriturus/ktra:latest
```

Or, if you want to pull a fixed version image, try this.  

```
docker pull ghcr.io/moriturus/ktra:0.4.3
```

> ***Note***:  
> The latest published `Ktra` version is [![ktra at crates.io](https://img.shields.io/crates/v/ktra.svg)](https://crates.io/crates/ktra).

---

### Tags

There are several images tagged with features and releases.  
Any commit on `develop` branch builds images listed below:

- `latest`
    - `db-sled` featured image.
- `db-redis-latest`
    - `db-redis` featured image.
- `db-mongo-latest`
    - `db-mongo` featured image.


Similarly, images below are built automatically when tags are pushed:

- `{VERSION}` *(e.g. `0.4.3`)*
    - `db-sled` featured image.
- `db-redis-{VERSION}`
    - `db-redis` featured image.
- `db-mongo-{VERSION}`
    - `db-mongo` featured image.

---

### Registry

All of the docker images are built with [emk/rust-musl-builder](https://github.com/emk/rust-musl-builder) image and stored at [GitHub Container Registry](https://docs.github.com/en/free-pro-team@latest/packages/getting-started-with-github-container-registry/about-github-container-registry).  
These are public images so you can pull them without any authentication.