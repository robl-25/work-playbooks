# Atom playbook

This playbook installs [atom](https://atom.io/), its dependencies and some packages.
The installation process involves add key for atom repository and its repository
with apt command. Then it will be possible to use atom with `apt`.

## Variables
This playbook install some packages for atom by default. They are:
- atom-ide-ui
- busy-signal
- git-blame
- go-imports
- ide-golang
- ide-gopls
- ide-python
- intentions
- language-terraform
- linter-eslint
- linter-flake8
- linter-ui-default
- linter

If you want, you can use the variable `atom_packages` in the main file to overwrite
the default. For example:
```yaml
- name: Install atom
  import_playbook: playbooks/atom-playbook.yml
  vars:
    atom_packages:
      - atom-ide-ui
```
To not install packages use empty list, passing `[]`.

**Observation**: This playbook create a symbolic link to use python3 as python.
