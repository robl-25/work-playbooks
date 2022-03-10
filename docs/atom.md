# Atom playbook

This playbook installs [atom](https://atom.io/), its dependencies and some packages.
The installation process involves add key for atom repository and its repository
with apt command. Then it will be possible to use atom with `apt`.
For the packages, you can choose or let it install the default packages. The default packages are:
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

If you want to choose the packages in the main file use the variable `atom_packages`. For example:
```yaml
- name: Install atom
  import_playbook: playbooks/atom-playbook.yml
  vars:
    atom_packages:
      - atom-ide-ui
```
For empty list, you can just pass `[]`.

**Observation**: This playbook create a symbolic link to use python3 as python.
