# Forticlient

Used in my company as VPN, [forticlient](https://www.fortinet.com/products/endpoint-security/forticlient) is installed from the official repository in debian based systems.
After installing, this playbook will configure the credentials and it can add a cron
to connect if it disconnects for any reason.

## Variables
To configure the VPN is necessary that all this variables are defined, otherwise
the playbook will skip this step and this service can have problems to work. To
configure use:
```yaml
- name: Install forticlient
  import_playbook: playbooks/forticlient-playbook.yml
  vars:
    host: "<YOUR_HOST>"
    cert: "<YOUR_CERTIFICATE>"
    port: <YOUR_PORT>
    realm: <YOUR_REALM>
```
In addition, this playbook can configure a cron job to always reconnect if the VPN
disconnects. To use you need the variables above and `with_cron` variable as `true`.
For example:
```yaml
- name: Install forticlient
  import_playbook: playbooks/forticlient-playbook.yml
  vars:
    host: "<YOUR_HOST>"
    cert: "<YOUR_CERTIFICATE>"
    port: <YOUR_PORT>
    realm: <YOUR_REALM>
    with_cron: true
```

## Hard coded variables
- password: ansible will get your sudo password as VPN password
- username: ansible will get the user used to run this playbook as the VPN user
