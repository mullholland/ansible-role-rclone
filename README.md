# [rclone](#rclone)

|GitHub|GitLab|
|------|------|
|[![github](https://github.com/mullholland/ansible-role-rclone/workflows/Ansible%20Molecule/badge.svg)](https://github.com/mullholland/ansible-role-rclone/actions)|[![gitlab](https://gitlab.com/mullholland/ansible-role-rclone/badges/main/pipeline.svg)](https://gitlab.com/mullholland/ansible-role-rclone)|

description

## [Role Variables](#role-variables)

These variables are set in `defaults/main.yml`:
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


## [Example Playbook](#example-playbook)

This example is taken from `molecule/default/converge.yml` and is tested on each push, pull request and release.
```yaml
---
- name: Converge
  hosts: all
  become: true
  gather_facts: true

  roles:
    - role: "mullholland.rclone"
```





## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/mullholland):

-   [debian10](https://hub.docker.com/r/mullholland/docker-molecule-debian10)
-   [debian11](https://hub.docker.com/r/mullholland/docker-molecule-debian11)
-   [ubuntu1804](https://hub.docker.com/r/mullholland/docker-molecule-ubuntu1804)
-   [ubuntu2004](https://hub.docker.com/r/mullholland/docker-molecule-ubuntu2004)
-   [ubuntu2204](https://hub.docker.com/r/mullholland/docker-molecule-ubuntu2204)
-   [centos7](https://hub.docker.com/r/mullholland/docker-molecule-centos7)
-   [centos-stream8](https://hub.docker.com/r/mullholland/docker-molecule-centos-stream8)
-   [centos-stream9](https://hub.docker.com/r/mullholland/docker-molecule-centos-stream9)
-   [ubi8](https://hub.docker.com/r/mullholland/docker-molecule-ubi8)
-   [fedora35](https://hub.docker.com/r/mullholland/docker-molecule-fedora35)
-   [fedora36](https://hub.docker.com/r/mullholland/docker-molecule-fedora36)
-   [amazonlinux](https://hub.docker.com/r/mullholland/docker-molecule-amazonlinux)
-   [rockylinux8](https://hub.docker.com/r/mullholland/docker-molecule-rockylinux8)
-   [almalinux8](https://hub.docker.com/r/mullholland/docker-molecule-almalinux8)
-   [almalinux9](https://hub.docker.com/r/mullholland/docker-molecule-almalinux9)

The minimum version of Ansible required is 2.10, tests have been done to:

-   The previous versions.
-   The current version.

This Role has the following additional molecule test scenarios:
-   custom_version

Details can be found in ```molecule/```




If you find issues, please register them in [GitHub](https://github.com/mullholland/ansible-role-rclone/issues)

## [License](#license)

MIT


## [Author Information](#author-information)

[Mullholland](https://github.com/mullholland)

## [Special Thanks](#special-thanks)

Template inspired by [Robert de Bock](https://github.com/robertdebock)
