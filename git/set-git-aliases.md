# Setting up git aliases

Basically you just need to add lines to ~/.gitconfig

```bash

[alias]
    st = status
    ci = commit -v

```
Or you can use the git config alias command:

```bash

$ git config --global alias.st status 

```
On unix, use single quotes if the alias has a space:

```bash
$ git config --global alias.ci 'commit -v'
```

On windows, use double quotes if the alias has a space or a command line argument:

```bash
c:\dev> git config --global alias.ci "commit -v"
```

The alias command even accepts functions as parameters.
