# [Moonswitch - Zero to Prod](https://play.instruqt.com/moonswitch/invite/wymkew67tkza)
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
    git config pull.rebase true
    git push --set-upstream origin main
    git remote add origin https://github.com/pythoninthegrass/zero_to_prod.git
    git branch -M main
    git add .
    git status
    git commit -m "init"
    git push --set-upstream origin main
    ```
* Terraform aliases
  * Add to ~/.bashrc
    ```bash
    # append to ~/.bash_aliases
    cat << 'EOF' >> ~/.bash_aliases
    alias k=kubectl
    alias tf="terraform"
    alias tfi="terraform init"
    alias tff="terraform fmt"
    alias tfv="terraform validate"
    alias tfp="terraform plan"
    alias tfa="terraform apply"
    EOF

    # sed remove 'alias kc=kubectl' (if found)
    sed -i '/alias kc=kubectl/d' ~/.bash_aliases

    # source new aliases
    source ~/.bashrc
    ```
* Terraform workflow
    ```bash
    tf init         # tfi
    tf fmt
    tf validate     # tfv
    tf plan         # tfp
    tf apply        # tfa
    ```

## TODO
* [Issues](https://github.com/pythoninthegrass/zero_to_prod/issues)
* `Makefile`

## Further Reading
[moonswitch/workshop-code](https://github.com/moonswitch/workshop-code/tree/main)
