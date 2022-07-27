# Install With Cargo

You can install `Ktra` simply with just running a command below.  
This command will install the default `Ktra` enabled `secure-auth` and `db-sled` features.

```
cargo install ktra
```

## Change database implementation

If you want to select the backended database:

* `db-redis` 

```
cargo install ktra --no-default-features --features=secure-auth,db-redis
```

* `db-mongo` 

```
cargo install ktra --no-default-features --features=secure-auth,db-mongo
```

## Add openid support

Openid support can be added with the extra "openid" feature, which is not compatible with `secure-auth`:

``` bash
cargo install ktra --no-default-features --features=openid
```
You can add other `db-*` features to change the backing database implementation as above.
