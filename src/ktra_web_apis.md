# Appendix: Ktra Web APIs

`Ktra Web APIs` are extra web APIs that are not specified in the [specification](https://doc.rust-lang.org/cargo/reference/registries.html) but required to manage users.  

## Login/Password users API
Since all APIs send passwords in ***cleartext***, it is highly recommended that
you connect the registry from your local network only *OR* use an HTTPS
connection.

### Create a new user

- Specification

<table>
    <tr>
        <td>Endpoint</td>
        <td>/ktra/api/v1/new_user/{user_name}</td>
    </tr>
    <tr>
        <td>Method</td>
        <td>POST</td>
    </tr>
    <tr>
        <td>Body</td>
        <td>{ "password": "PASSWORD" }</td>
    </tr>
</table>

- Response

```json
{
    "token": "TOKEN"
}
```

### Login

- Specification

<table>
    <tr>
        <td>Endpoint</td>
        <td>/ktra/api/v1/login/{user_name}</td>
    </tr>
    <tr>
        <td>Method</td>
        <td>POST</td>
    </tr>
    <tr>
        <td>Body</td>
        <td>{ "password": "PASSWORD" }</td>
    </tr>
</table>

- Response

```json
{
    "token": "NEW TOKEN"
}
```

### Change password

- Specification

<table>
    <tr>
        <td>Endpoint</td>
        <td>/ktra/api/v1/change_password/{user_name}</td>
    </tr>
    <tr>
        <td>Method</td>
        <td>POST</td>
    </tr>
    <tr>
        <td>Body</td>
        <td>{ "old_password": "OLD PASSWORD", "new_password": "NEW PASSWORD" }</td>
    </tr>
</table>

- Response

```json
{
    "token": "NEW TOKEN"
}
```

### Crates.io Mirroring

> ***Note***:  
> This API can be available when ***crates-io-mirroring*** feature is enabled.


- Specification

<table>
    <tr>
        <td>Endpoint</td>
        <td>/ktra/api/v1/mirror/{crate_name}/{version}/download</td>
    </tr>
    <tr>
        <td>Method</td>
        <td>GET</td>
    </tr>
    <tr>
        <td>Body</td>
        <td>-</td>
    </tr>
</table>

- Response

Binary file.

## OpenId API
When using the [OpenId](./quick_start/openid.md) feature, you do not have any of
the insecure user management endpoints active, and instead you get one endpoint
to see your existing token/create a new one, and one endpoint to revoke your old
token replacing it with a new one.

As the token end up being sent in cleartext still, it is still recommended to be
either inside a small, trusted VPN or use HTTPS, or both.

For both endpoints, you will go through an OpenId authentication flow, so unless
you already have an opened session, you must call this endpoint interactively.

### See existing token, creating it for first time users

This is the same endpoint as the one being exposed for the `cargo login` flow

- Specification

<table>
    <tr>
        <td>Endpoint</td>
        <td>/me</td>
    </tr>
    <tr>
        <td>Method</td>
        <td>GET</td>
    </tr>
</table>

- Response

If the user already had a token:
```json
{
    "username": "issuer:user_identity",
    "existing_token": "SOME TOKEN"
}
```

If the user never had a token:
```json
{
    "username": "issuer:user_identity",
    "new_token": "SOME TOKEN",
    "revoked_token": null
}
```

### Force token replacement

- Specification

<table>
    <tr>
        <td>Endpoint</td>
        <td>/replace_token</td>
    </tr>
    <tr>
        <td>Method</td>
        <td>GET</td>
    </tr>
</table>

- Response

```json
{
    "username": "issuer:user_identity",
    "new_token": "SOME TOKEN",
    "revoked_token": "A NOW INVALID TOKEN"
}
```
