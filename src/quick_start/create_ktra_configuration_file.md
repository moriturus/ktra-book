# Create Ktra Configuration File

### About

***Ktra Configuration File*** is a [TOML](https://en.wikipedia.org/wiki/TOML) formatted document file.  
To configure `Ktra`'s database, index and crate files, you should write it and pass the path to it as a command argument.

---

#### Sample

> ***Note 1***:  
> All configurations are listed on [Appendix: Configurations](../configurations.md) page.

> ***Note 2***:  
> *Please make sure your branch name AGAIN*.  
> `main` is the default on `GitHub` but `GitLab`, `Bitbucket` and other git repository hosting services might default to `master` instead of `main`.

```toml
[index_config]
remote_url = "https://github.com/YOUR_USERNAME/YOUR_INDEX.git"
https_username = "YOUR_USERNAME"
https_password = "GITHUB_ACCESS_TOKEN" 
branch = "main"
```

And run `Ktra` with passing the path to above file.

```
ktra -c /path/to/config/your_config.toml
```

- Please remember that `Ktra` searches `./ktra.toml` as a default configuration file if not specified.
