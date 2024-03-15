# checkmk

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&logoColor=white)](https://github.com/rolehippie/checkmk)
[![General Workflow](https://github.com/rolehippie/checkmk/actions/workflows/general.yml/badge.svg)](https://github.com/rolehippie/checkmk/actions/workflows/general.yml)
[![Readme Workflow](https://github.com/rolehippie/checkmk/actions/workflows/docs.yml/badge.svg)](https://github.com/rolehippie/checkmk/actions/workflows/docs.yml)
[![Galaxy Workflow](https://github.com/rolehippie/checkmk/actions/workflows/galaxy.yml/badge.svg)](https://github.com/rolehippie/checkmk/actions/workflows/galaxy.yml)
[![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/checkmk)](https://github.com/rolehippie/checkmk/blob/master/LICENSE)
[![Ansible Role](https://img.shields.io/badge/role-rolehippie.checkmk-blue)](https://galaxy.ansible.com/rolehippie/checkmk)

Ansible role to install CheckMK server or satellite.

## Sponsor

Building and improving this Ansible role have been sponsored by my current and previous employers like **[Cloudpunks GmbH](https://cloudpunks.de)** and **[Proact Deutschland GmbH](https://www.proact.eu)**.

## Table of content

- [Requirements](#requirements)
- [Default Variables](#default-variables)
  - [checkmk_admin_password](#checkmk_admin_password)
  - [checkmk_default_folders](#checkmk_default_folders)
  - [checkmk_default_labels](#checkmk_default_labels)
  - [checkmk_default_publish](#checkmk_default_publish)
  - [checkmk_default_volumes](#checkmk_default_volumes)
  - [checkmk_extra_folders](#checkmk_extra_folders)
  - [checkmk_extra_labels](#checkmk_extra_labels)
  - [checkmk_extra_publish](#checkmk_extra_publish)
  - [checkmk_extra_volumes](#checkmk_extra_volumes)
  - [checkmk_image](#checkmk_image)
  - [checkmk_livestatus_tcp](#checkmk_livestatus_tcp)
  - [checkmk_mail_relay_host](#checkmk_mail_relay_host)
  - [checkmk_network](#checkmk_network)
  - [checkmk_pull_image](#checkmk_pull_image)
  - [checkmk_site_id](#checkmk_site_id)
  - [checkmk_version](#checkmk_version)
- [Discovered Tags](#discovered-tags)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Requirements

- Minimum Ansible version: `2.10`

## Default Variables

### checkmk_admin_password

Password for the admin user

#### Default value

```YAML
checkmk_admin_password:
```

### checkmk_default_folders

List of default folders to create

#### Default value

```YAML
checkmk_default_folders:
  - /var/lib/checkmk
```

### checkmk_default_labels

List of default labels to assign to docker command

#### Default value

```YAML
checkmk_default_labels: []
```

### checkmk_default_publish

List of default port publishing

#### Default value

```YAML
checkmk_default_publish:
  - 5000:5000
  - 6557:6557
```

#### Example usage

```YAML
checkmk_default_publish:
  - 127.0.0.1:5000:5000
  - 127.0.0.1:6557:6557
```

### checkmk_default_volumes

List of default volumes to mount

#### Default value

```YAML
checkmk_default_volumes:
  - /var/lib/checkmk:/opt/omd/sites
```

### checkmk_extra_folders

List of extra folders to create

#### Default value

```YAML
checkmk_extra_folders: []
```

#### Example usage

```YAML
checkmk_extra_folders:
  - /path/to/host/folder1
  - /path/to/host/folder2
  - /path/to/host/folder3
```

### checkmk_extra_labels

List of extra labels to assign to docker command

#### Default value

```YAML
checkmk_extra_labels: []
```

### checkmk_extra_publish

List of extra port publishing

#### Default value

```YAML
checkmk_extra_publish: []
```

#### Example usage

```YAML
checkmk_extra_publish:
  - 8080:8080
  - 127.0.0.1:9000:9000
```

### checkmk_extra_volumes

List of extra volumes to mount

#### Default value

```YAML
checkmk_extra_volumes: []
```

#### Example usage

```YAML
checkmk_extra_volumes:
  - /path/to/host/folder1:/path/within/container1
  - /path/to/host/folder2:/path/within/container2
  - /path/to/host/folder3:/path/within/container3
```

### checkmk_image

Docker image to use for deployment

#### Default value

```YAML
checkmk_image: checkmk/check-mk-raw:{{ checkmk_version }}
```

### checkmk_livestatus_tcp

Enable livestatus via TCP

#### Default value

```YAML
checkmk_livestatus_tcp: true
```

### checkmk_mail_relay_host

Host of an SMTP relay server

#### Default value

```YAML
checkmk_mail_relay_host:
```

### checkmk_network

Optionally assign this Docker network to container

#### Default value

```YAML
checkmk_network:
```

### checkmk_pull_image

Pull image as part of the tasks

#### Default value

```YAML
checkmk_pull_image: true
```

### checkmk_site_id

Site name of the CheckMK server

#### Default value

```YAML
checkmk_site_id:
```

### checkmk_version

Version of CheckMK to use

#### Default value

```YAML
checkmk_version: 2.3.0-latest
```

## Discovered Tags

**_checkmk_**


## Dependencies

- [rolehippie.docker](https://github.com/rolehippie/docker)
- [community.docker](https://github.com/ansible-collections/community.docker)

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
