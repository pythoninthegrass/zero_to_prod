# Moonswitch - Zero to Prod

## Quickstart
* Setup git repo
```bash
# install gh cli
type -p curl >/dev/null || (sudo apt update && apt install curl -y)
curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg \
&& chmod go+r /usr/share/keyrings/githubcli-archive-keyring.gpg \
&& echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
&& apt update && apt install gh -y

# login
gh auth login
git push --set-upstream origin main
git remote add origin https://github.com/pythoninthegrass/zero_to_prod.git
git branch -M main
git add .
git status
git commit -m "init"
git push --set-upstream origin main
```
* Terraform workflow
```bash
alias tf="terraform"
tf init
tf fmt
tf validate
tf plan
tf apply
```