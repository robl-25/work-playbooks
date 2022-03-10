# Docker Compose

Install [docker compose](https://docs.docker.com/compose/) if necessary. This playbook
will check if docker compose is installed, if it is, the version. After, it will get
the latest version. If docker compose is not installed or the latest version is bigger
than installed one, this package will be installed from the github page.

## Variables
For this playbook, the variables are:
- github_url: url for the official github page to download docker compose
- platform: the platform used in this playbook. It is hardcoded as `Linux-x86_64`
