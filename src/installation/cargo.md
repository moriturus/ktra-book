# Install With Cargo

You can install `Ktra` simply with just running a command below.  
This command will install the default `Ktra` enabled `secure-auth` and `db-sled` features.

```
cargo install ktra
```

If you want to select the backended database:

* `db-redis` 

```
cargo install ktra --no-default-features features=secure-auth,db-redis
```

* `db-mongo` 

```
cargo install ktra --no-default-features features=secure-auth,db-mongo
```
