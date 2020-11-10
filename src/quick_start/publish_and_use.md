# Publish And Use

🎉 Congratulations!  
It's time to publish your first and private crate!

---

### 1. Create a new crate and publish

Just run:

> ***Note 1***:  
> `ktra` in below command is the registry name you specified in `.cargo/config.toml` file.

> ***Note 2***:  
> `--allow-dirty` option is not needed if your local repository is clean.

```
cargo new my_crate --lib
cd my_crate
cargo publish --allow-dirty --registry=ktra
```

If you get no errors your publishing has done perfectly.

---

### 2. Use your crate

To use your published crate from another one, you just specify a registry at `dependencies` section in `Cargo.toml`.

```toml
[package]
name = "my_another_crate"
version = "0.1.0"
authors = ["alice <alice@example.com>"]
edition = "2018"

[dependencies]
my_crate = { version = "0.1", registry = "ktra" }
```