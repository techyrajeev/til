# Setting up git standup aliase

Basically you just need to add lines to ~/.gitconfig

```bash
[alias]
    st = status
    ci = commit -v
    standup = !"git log --reverse --branches --since=$(if [[ "Mon" == "$(date +%a)" ]]; then echo "last friday"; else echo "yesterday"; fi) --author=$(git config --get user.email) --format=format:'%C(cyan) %ad %C(yellow)%h %Creset %s %Cgreen%d' --date=local"
```

