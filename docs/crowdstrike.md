# CrowdStrike

Download crowdstrike from google drive file and install it. After, using
`ansible_crowdstrike_cid` variable, this playbook will set this CID to crowdstrike.
Than, it will start the service.

## Variables
In this playbook, you can pass `ansible_crowdstrike_cid` variable. This variable is
used to configure crowdstrike. It is optional. If not passed the cid won't be
configured and this service can have problems to work. It should be used in the main
file, like:
```yaml
- name: Install crowdstrike
  import_playbook: playbooks/crowdstrike-playbook.yml
  vars:
    ansible_crowdstrike_cid: "<YOUR-CID>"
```

## Hard coded variables
- gdown_url: define [gdown](https://pypi.org/project/gdown/) package url.
- gdown_path: where to save to save gdown package.
- url: google drive url to download crowdstrike.
- deb_path: where and which name save crowdstrike package.
