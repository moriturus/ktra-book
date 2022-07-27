# Appendix: Configurations

> ***Note***:  
> All configurations are able to set via command arguments. See `ktra -h` for more details.

### About Index Configurations

`index_config` has these configurations:

- `remote_url`
    - The essential configuration.
    - Sets a URL for the remote index git repository.
- `local_path`
    - The default value is `./index`
    - Sets a path for local index git repository.
- `branch`
    - The default value is `main`.
    - Sets a branch name of the index git repository.
- `https_username`
    - *Required unless you use SSH protocol*.
    - Sets a username to use for the authentication.
- `https_password`
    - *Required unless you use SSH protocol*.
    - Sets a password to use for the authentication.
- `ssh_privkey_path`
    - *Required unless you use HTTPS protocol*.
    - Sets a private key path to use for the authentication.
- `ssh_key_passphrase`
    - *Optional*.
    - Sets a private key's passphrase to use for authentication if the remote index git repository uses SSH protocol.
- `ssh_pubkey_path`
    - *Optional*.
    - Sets a public key path to use for authentication if the remote index git repository uses SSH protocol.
- `ssh_username`
    - *Optional*.
    - Sets a username to use for authentication if the remote index git repository uses SSH protocol.
- `git_email`
    - The default value is `undefined@example.com`.
    - Sets an author and committer email address.
- `git_name`
    - The default value is `ktra-driver`.
    - Sets an author and committer name.

### About Crate Files Configurations

`crate_files_config` is *optional* and it has these configurations:

- `dl_dir_path`
    - The default value is `./crates`.
    - Sets the crate files directory.
- `cache_dir_path`
    - *`crates-io-mirroring` feature needed.*
    - The default value is `./crates_io_caches`.
    - Sets the cache files directory.
- `dl_path`
    - The default value is `["dl"]`.
    - Sets crate file download paths.
        - *Sample*: `["path", "to", "download"]` to be `https://example.com/path/to/download`
        - This configuration *MUST* correspond with the `dl` field's value in `config.json` at the index git repository.

### About Database Configurations

`db_config` is *optional* and it has these configurations:

- `db_dir_path`
    - The default value is `db` if you use `db-sled` feature.
    - Sets a database directory.
- `redis_url`
    - The default value is `redis://localhost` if you use `db-redis` feature.
    - Sets a Redis URL. *This can contain a username and password phrase to use the authentication*.
- `mongodb_url`
    - The default value is `redis://localhost:27017` if you use `db-mongo` feature.
    - Sets a Redis URL. *This can contain a username and password phrase to use the authentication*.
- `login_prefix`
    - The default value, for backwards compatible reasons, is `ktra-secure-auth:`
    - Sets a prefix to the usernames in the database/registry.

### About Server Configurations

`server_config` is *optional* and it has these configurations:

- `address`
    - The default value is `[0, 0, 0, 0]`.
    - Sets an address HTTP server runs.
- `port`
    - The default value is `8000`.
    - Sets a port number HTTP server listens.

### About OpenId Configurations

`openid_config` is *optional* and it has these configurations:
- `issuer_url`
   - Mandatory if `openid_config` is specified
   - Sets the URL of the Identity Provider to use
- `redirect_url`
   - Mandatory if `openid_config` is specified
   - Sets the base URL to use in the redirect URI for the authentication flow.
     This should match the URL ktra is exposed to, in order to comply with
     redirect URL verifications done by the Identity Provider.
- `client_id`
   - Mandatory if `openid_config` is specified
   - Sets the ID of the ktra application as registered on the Identity Provider.
- `client_secret`
   - Mandatory if `openid_config` is specified
   - Sets the secret of the ktra application as registered on the Identity
     Provider.
- `additional_scopes`
   - Default is an empty list
   - Sets the additional scopes queried by the application for OpenId. Usually
     this value depends on the issuer.
- `gitlab_authorized_groups`
   - Default is unset
   - Sets the authorized Gitlab groups whose members are allowed to create an
     account on the registry and be publishers/owners. Leave empty or unset not
     to check groups.
- `gitlab_authorized_users`
   - Default is unset
   - Sets the authorized Gitlab users who are allowed to create an account on
     the registry and be publishers/owners. Leave empty or unset not to check
     users.
