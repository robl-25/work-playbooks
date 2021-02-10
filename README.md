# work-playbooks
Playbooks to install packages for work

## How to use
First, install [ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) in your machine. Then, run
`ansible-playbook main.yml -e ansible_become_password=<YOUR_PASSWORD> -e ansible_fortihost=<FORTICLIENT_HOST> -e ansible_cert=<YOUR_VPN_CERTIFICATE>`.

Obs.: `ansible_fortihost` and `ansible_cert` are variables used in forticlient-playbook,
if you won't use this playbook, you don't need to use this variables.

## For new systems
### Sudoers Group
For default debian doesn't include your user in sudoers group. To include, first login as root. Then type `sudo usermod -aG sudo <username>`.

### Debian Repository
If your instalation is old, you can just update the repositories to get new version of the packages. For new versions edit `/etc/apt/sources.list` with:
```
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
