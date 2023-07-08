# [rclone](#rclone)

Install and configure rclone

|GitHub|GitLab|Quality|Downloads|Version|
|------|------|-------|---------|-------|
|[![github](https://github.com/mullholland/ansible-role-rclone/workflows/Ansible%20Molecule/badge.svg)](https://github.com/mullholland/ansible-role-rclone/actions)|[![gitlab](https://gitlab.com/opensourceunicorn/ansible-role-rclone/badges/master/pipeline.svg)](https://gitlab.com/opensourceunicorn/ansible-role-rclone)|[![quality](https://img.shields.io/ansible/quality/59780)](https://galaxy.ansible.com/mullholland/rclone)|[![downloads](https://img.shields.io/ansible/role/d/59780)](https://galaxy.ansible.com/mullholland/rclone)|[![Version](https://img.shields.io/github/release/mullholland/ansible-role-rclone.svg)](https://github.com/mullholland/ansible-role-rclone/releases/)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/mullholland/ansible-role-rclone/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  become: true
  gather_facts: true

  roles:
    - role: "mullholland.rclone"
```


## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/mullholland/ansible-role-rclone/blob/master/defaults/main.yml):

```yaml
---
# release of rclone to use.
# 'latest'  => always gets the latest version of rclone
# 'custom'  => lets you define a version to install
rclone_release: "latest"

# ATM only linux ist tested/supported by the role
# rclone supports many others
# https://rclone.org/downloads/
rclone_os: "linux"

# which version to install if not "latest"
rclone_version: '1.59.0'

# Download URL for latest/custom rclone
# change if you need custom URLs
rclone_download_url_latest: "https://downloads.rclone.org/rclone-current-{{ rclone_os }}-{{ rclone_arch }}.zip"
rclone_download_url_custom: "https://downloads.rclone.org/v{{ rclone_version }}/rclone-v{{ rclone_version }}-{{ rclone_os }}-{{ rclone_arch }}.zip"

# where to install
rclone_bin_path: "/usr/local/bin"

# where to store configs
# https://rclone.org/docs/#config-config-file
# defaults to `~/.config/rclone/rclone.conf`
# to make it more "portable" the variable `rclone_bin_path`can be used to store the config alongside the binary
# rclone_conf_path: "{{ rclone_bin_path }}"
# in this case the folder will not be created/touched by ansible
rclone_conf_path: "~/.config/rclone"

# https://rclone.org/docs/
rclone_config: []
# rclone_config:
#   - name: "WebDAV"
#     options:
#       - "type = webdav"
#       - "url = https://nextcloud.domain.tld/remote.php/dav/files/username/"
#       - "vendor = nextcloud"
#       - "user = username"
#       - "bearer_token = SuperSecretToken"
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/mullholland/ansible-role-rclone/blob/master/requirements.txt).


## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://mullholland.net) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/mullholland/ansible-role-rclone/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/mullholland):

|container|tags|
|---------|----|
|[EL](https://hub.docker.com/repository/docker/mullholland/docker-centos-systemd/general)|all|
|[Amazon](https://hub.docker.com/repository/docker/mullholland/docker-amazonlinux-systemd/general)|Candidate|
|[Fedora](https://hub.docker.com/repository/docker/mullholland/docker-fedora-systemd/general)|all|
|[Ubuntu](https://hub.docker.com/repository/docker/mullholland/docker-ubuntu-systemd/general)|all|
|[Debian](https://hub.docker.com/repository/docker/mullholland/docker-debian-systemd/general)|all|

The minimum version of Ansible required is 2.10, tests have been done to:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them in [GitHub](https://github.com/mullholland/ansible-role-rclone/issues)

## [License](#license)

[MIT](https://github.com/mullholland/ansible-role-rclone/blob/master/LICENSE).

## [Author Information](#author-information)

[Mullholland](https://mullholland.net)

Please consider [sponsoring me](https://github.com/sponsors/mullholland).
