# Create Index Git Repository

The ***Index Repository*** serves data read by `cargo` command when you build a crate depending on another crate hosted on `Ktra`.  
You can use any *git repository hosting service* such as [GitHub](https://github.com), [GitLab](https://gitlab.com) and [Bitbucket](https://bitbucket.org/) even if its repository is private.  
Additionally, of course, you can use private git repository managed by yourself.

---

This book introduces the simplest way to create the index repository with *GitHub*.  

### 1. Go to [Create new repository page](https://github.com/new). (*login needed*)

For more details, please see [GitHub official documents](https://docs.github.com/en/free-pro-team@latest/github/creating-cloning-and-archiving-repositories/creating-a-new-repository).
- The index repository's name is arbitrary.
- Public or private either is fine.

---

### 2. Clone the repository created above.

> ***Note***:  
> You have to create an *access token* in advance to clone with HTTPS protocol.  
> Please see the [GitHub official documents](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/creating-a-personal-access-token).

```
git clone https://github.com/YOUR_USERNAME/YOUR_INDEX.git
```

---

### 3. Create `config.json` file then commit and push it to remote repository.

> ***Note***:  
> *Please make sure your branch name*.  
> `main` is the default on `GitHub` but `GitLab`, `Bitbucket` and other git repository hosting services might default to `master` instead of `main`.

```
cd YOUR_INDEX
echo '{"dl":"http://localhost:8000/dl","api":"http://localhost:8000"}' > config.json
git add config.json
git commit -am "initial commit"
git push origin main
```

---

### 4. Edit your `.cargo/config.toml`.

> ***Note 1***:  
> Please see [Cargo official documents](https://doc.rust-lang.org/cargo/reference/registries.html#using-an-alternate-registry) for more details.

> ***Note 2***:  
> To make git remember your credential, please use the [credential helper](https://docs.github.com/en/free-pro-team@latest/github/using-git/caching-your-github-credentials-in-git).

```toml
[registries]
ktra = { index = "https://github.com/YOUR_USERNAME/YOUR_INDEX.git" }
```