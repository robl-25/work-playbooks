# Docker

Install [docker](https://www.docker.com/) from official repository. This playbook
use [this](https://docs.docker.com/engine/install/debian/) page to install docker.
Before installing docker, this playbook install all required system packages. Than,
add docker GPG key from official repository. After, add docker-ce repository to apt.
Finally, it will install docker, run and enable to run in the background.
After docker is installed, the playbook will install docker module for python using
python3 as interpreter.
This part is necessary to use docker without sudo, for more information access
[this](https://docs.docker.com/engine/install/linux-postinstall/). It create docker
group, add current user in this group and change docker directory ownership and
permissions to current user.

## Variables
- ansible_python_interpreter: explicitly uses python3 as interpreter. (More information)[https://docs.ansible.com/ansible/latest/reference_appendices/python_3_support.html#using-python-3-on-the-managed-machines-with-commands-and-playbooks]
- repository: stable docker repository
- gpg_key: url for gpg key to be added using `apt_key`.
