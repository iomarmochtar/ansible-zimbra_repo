# Zimbra Local Repository Setup

Automating the setup of zimbra local repository as described in [Zimbra's Wiki](https://wiki.zimbra.com/wiki/Zimbra_Collaboration_repository#How_to_create_a_local_repository).

## Install

```bash
ansible-galaxy install iomarmochtar.zimbra_repo
```

## Requirements

- Internet access to fetch the repo packages
- Selinux disabled
- Make sure the destinated host has sufficient space to download all package.

## Role Variables

You can see used variables in file **defaults/main.yml**, but the required vars are:

- repo_version
- repo_package (rpm or deb)

Set variable **zimbra_installer_url** if you want also download the zimbra installer package that will be put in repository directory. it's very useful for multiserver installation for not redownload the package.

## Example Playbook

```yaml
- hosts: repo_server
  roles:
    - role: iomarmochtar.zimbra_repo
      repo_version: 885
      repo_package: rpm
```

## License

GNU GPL v3.0

## Author Information

```
Author: Imam Omar Mochtar
Email: iomarmochtar@gmail.com
Website: https://blog.mochtar.net
```
