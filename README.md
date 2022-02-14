# work-playbooks
Playbooks to install packages for work

## How to use
First, install [ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) in your machine. Then, run
`ansible-playbook main.yml [variables]`.

### Variables
For each variable use this format `-e name=value`. Available variables are:
- ansible_become_password: sudo password. Required.
- ansible_fortihost: host used in forticlient. Optional. If not passed forticlient won't be configured and this service can have problems to work.
- ansible_forticert: certificate used in forticlient connection. Optional. If not passed forticlient won't be configured and this service can have problems to work.
- ansible_crowdstrike_cid: cid used in crowdstrike. Optional. If not passed the cid won't be configured and this service can have problems to work.

## For new systems
### Sudoers Group
#### Debian
For default debian doesn't include your user in sudoers group. To include, first login as root. Then type `sudo usermod -aG sudo <username>`.
#### Fedora
On Fedora, it is the wheel group the user has to be added to, as this group has full admin privileges. You can run `sudo usermod -aG wheel <username>`. If this doesn't work, you may have to edit the `/etc/sudoers` file to uncomment the line with the group name:
```
...
%wheel ALL=(ALL) ALL
...
```
You will need to logout and back in for changes to take effect.

### Debian Repository
If your instalation is old, you can just update the repositories to get new version of the packages. For new versions edit `/etc/apt/sources.list` with:
```bash
deb http://deb.debian.org/debian/ testing main non-free contrib
deb-src http://deb.debian.org/debian/ testing main non-free contrib

deb http://security.debian.org/debian-security stable/updates main contrib non-free
deb-src http://security.debian.org/debian-security stable/updates main contrib non-free

# stable-updates, previously known as 'volatile'
deb http://deb.debian.org/debian/ stable-updates main contrib non-free
deb-src http://deb.debian.org/debian/ stable-updates main contrib non-free
```

### Install git
To install git use `sudo apt install git-all`

### Install Ansible
Install ansible under python3. More information look [here](https://docs.ansible.com/ansible/latest/reference_appendices/python_3_support.html).
`sudo pip3 install ansible`
