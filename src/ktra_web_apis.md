# Appendix: Ktra Web APIs

`Ktra Web APIs` are extra web APIs that are not specified in the [specification](https://doc.rust-lang.org/cargo/reference/registries.html) but required to manage users.  
Since all APIs send passwords in ***cleartext***, it is highly recommended that you connect the registry from your local network only *OR* use an HTTPS connection.

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