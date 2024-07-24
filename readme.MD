```
# Function to get the current Git branch name
get_git_branch() {
  git_branch=$(git symbolic-ref --short HEAD 2>/dev/null)
  if [ -n "$git_branch" ]; then
    echo "%{$fg[green]%}($git_branch)%{$reset_color%}"
  fi
}

# Customize the prompt to include the Git branch name in green color
setopt PROMPT_SUBST
PROMPT='%n@%m:%~$(get_git_branch) %# '
```