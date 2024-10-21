# Ansible Role: Containerd

![](https://i.imgur.com/waxVImv.png)
### [View all Roadmaps](https://github.com/nholuongut/all-roadmaps) &nbsp;&middot;&nbsp; [Best Practices](https://github.com/nholuongut/all-roadmaps/blob/main/public/best-practices/) &nbsp;&middot;&nbsp; [Questions](https://www.linkedin.com/in/nholuong/)
<br/>

An Ansible Role that installs [containerd](https://containerd.io) on Linux.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    containerd_package: containerd.io
    containerd_package_state: present

Package name and state controls.

    containerd_service_state: started
    containerd_service_enabled: true

Service controls. You can install containerd but not have it running or enabled on boot by changing these defaults.

    containerd_config_default_write: true

Write containerd defaults to the containerd config.toml file.

    containerd_config_cgroup_driver_systemd: false

Set systemd as cgroup driver in config.toml. Only valid with `containerd_config_default_write: true`

    docker_apt_release_channel: stable
    docker_apt_arch: '{{ (ansible_architecture == "aarch64") | ternary("arm64", "amd64") }}'
    docker_apt_repository: "deb [arch={{ docker_apt_arch }}] https://download.docker.com/linux/{{ ansible_distribution | lower }} {{ ansible_distribution_release }} {{ docker_apt_release_channel }}"
    docker_apt_ignore_key_error: true
    docker_apt_gpg_key: https://download.docker.com/linux/{{ ansible_distribution | lower }}/gpg

Apt installation paramemeters, useful if you want to switch from the stable channel releases, or install on a different CPU architecture (e.g. `arm64`).

    docker_yum_repo_url: https://download.docker.com/linux/{{ (ansible_distribution == "Fedora") | ternary("fedora","centos") }}/docker-ce.repo
    docker_yum_repo_enable_nightly: '0'
    docker_yum_gpg_key: https://download.docker.com/linux/centos/gpg

Yum/DNF installation parameters, useful if you want to switch from the stable repository.

## Dependencies

None.

## Example Playbook

```yaml
- hosts: all
  roles:
    - nholuong.containerd
```

# 🚀 I'm are always open to your feedback.  Please contact as bellow information:
### [Contact ]
* [Name: nho Luong]
* [Skype](luongutnho_skype)
* [Github](https://github.com/nholuongut/)
* [Linkedin](https://www.linkedin.com/in/nholuong/)
* [Email Address](luongutnho@hotmail.com)

![](https://i.imgur.com/waxVImv.png)
![](Donate.png)
[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/nholuong)

# License
* Nho Luong (c). All Rights Reserved.🌟