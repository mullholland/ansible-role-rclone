# [Ansible role ansible-generator](#ansible-generator)

Install and configure rclone

|GitHub|Downloads|Version|
|------|---------|-------|
|[![github](https://github.com/mullholland/ansible-role-ansible-generator/actions/workflows/molecule.yml/badge.svg)](https://github.com/mullholland/ansible-role-ansible-generator/actions/workflows/molecule.yml)|[![downloads](https://img.shields.io/ansible/role/d/mullholland/ansible-generator)](https://galaxy.ansible.com/mullholland/ansible-generator)|[![Version](https://img.shields.io/github/release/mullholland/ansible-role-ansible-generator.svg)](https://github.com/mullholland/ansible-role-ansible-generator/releases/)|
## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/mullholland/ansible-role-ansible-generator/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  gather_facts: true
  roles:
    - role: "{{ lookup('env', 'MOLECULE_PROJECT_DIRECTORY') }}"
```


## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/mullholland/ansible-role-ansible-generator/blob/master/defaults/main.yml):

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

- pip packages listed in [requirements.txt](https://github.com/mullholland/ansible-role-ansible-generator/blob/master/requirements.txt).


## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://mullholland.net) for further information.

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/mullholland):

|container|tags|
|---------|----|
|[EL](https://hub.docker.com/r/mullholland/enterpriselinux)|all|
|[Rocky](https://hub.docker.com/r/mullholland/rockylinux)|all|
|[AlmaLinux](https://hub.docker.com/r/mullholland/almalinux)|all|
|[Amazon](https://hub.docker.com/r/mullholland/amazonlinux)|all|
|[Fedora](https://hub.docker.com/r/mullholland/fedora/)|all|
|[Ubuntu](https://hub.docker.com/r/mullholland/ubuntu)|all|
|[Debian](https://hub.docker.com/r/mullholland/debian)|all|
|[CentOS](https://hub.docker.com/r/mullholland/centos)|all|

The minimum version of Ansible required is 2.10, tests have been done to:

- The version before the previous version.
- The previous version.
- The current version.

If you find issues, please register them in [GitHub](https://github.com/mullholland/ansible-role-ansible-generator/issues).

## [License](#license)

[MIT](https://github.com/mullholland/ansible-role-ansible-generator/blob/master/LICENSE).

## [Author Information](#author-information)

[Mullholland](https://mullholland.net)
