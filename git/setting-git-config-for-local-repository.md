# How to set config variables such as user-name and email for local-repository?

You can change the email address associated with commits you make in a single
repository. This will override your global Git config settings in this one
repository, but will not affect any other repositories.

```bash
$ git config user.email "email@example.com"
$ git config user.name "name"
...
```

