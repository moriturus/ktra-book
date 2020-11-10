# Create User And Login

`Ktra` has several additional web APIs called ***Ktra Web APIs*** to manage users.  
You should call these APIs to create a new user.

> ***Note***:  
> All APIs are listed and detailed on [Appendix: Ktra Web APIs](../ktra_web_apis.md) page.

---

### 1. Create a new user

Run this command. *[curl](https://curl.se/) command required*.  
`ALICE` just means *the first user*. Of course you can use a username you like.

```
curl -X POST -H 'Content-Type: application/json' -d '{"password":"PASSWORD"}' http://localhost:8000/ktra/api/v1/new_user/ALICE
```

Above command responds and prints a *new token* like this:

```json
{"token":"TOKEN"}
```

Please copy `TOKEN`, the printed token.

---

### 2. Login with `cargo` command

Run this command with the `TOKEN` that you copied.  

> ***Note***:  
> `ktra` in below command is the registry name you specified in `.cargo/config.toml` file.

```
cargo login --registry=ktra TOKEN
```

It's OK if you get this message:

```
Login token for `ktra` saved
```