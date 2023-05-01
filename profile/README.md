# We are McGill iGEM!
We do cool things with synthetic biology.

(Credit to my friend @notkaramel :'))
## Common commands for Git
>Make sure that you work on your branch and not on the `main` branch.

```bash
# Check the status of the repository.
# Attention to your current branch and files you modified/added.
# Attention to whether your branch(es) is behind/ahead of the GitHub repo.
git status

# Update the repository from remote repository
git pull

# Add all changes to the staging area
git add .  # or
git add -A
# Add a specific file to the staging area 
git add <file>

# Commit the changes in the staging area
git commit -m "Commit message"

# Push the changes to the remote repository
git push
```

## Checkout to your own branch
```bash
# Create a new branch
git checkout -b branch-name # replace branch-name with your own branch name

# For example:
git checkout -b emma
```

## Switch/Checkout to an existing branch
```bash
git checkout <branch name>	# or, on some machines
git switch <branch name>


# For example
git checkout main	# switch to main branch
git checckout emma	# switch to branch named "Emma"
```
