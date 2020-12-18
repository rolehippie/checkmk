# checkmk

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&logoColor=white)](https://github.com/rolehippie/checkmk) [![Build Status](https://img.shields.io/drone/build/rolehippie/checkmk/master?logo=drone)](https://cloud.drone.io/rolehippie/checkmk) [![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/checkmk)](https://github.com/rolehippie/checkmk/blob/master/LICENSE) 

Ansible role to install CheckMK server or satellite. 

## Sponsor 

[![Proact Deutschland GmbH](https://proact.eu/wp-content/uploads/2020/03/proact-logo.png)](https://proact.eu) 

Building and improving this Ansible role have been sponsored by my employer **Proact Deutschland GmbH**.

## Table of content

* [Default Variables](#default-variables)
  * [checkmk_admin_password](#checkmk_admin_password)
  * [checkmk_default_folders](#checkmk_default_folders)
  * [checkmk_default_labels](#checkmk_default_labels)
  * [checkmk_default_publish](#checkmk_default_publish)
  * [checkmk_default_volumes](#checkmk_default_volumes)
  * [checkmk_extra_folders](#checkmk_extra_folders)
  * [checkmk_extra_labels](#checkmk_extra_labels)
  * [checkmk_extra_publish](#checkmk_extra_publish)
  * [checkmk_extra_volumes](#checkmk_extra_volumes)
  * [checkmk_image](#checkmk_image)
  * [checkmk_livestatus_tcp](#checkmk_livestatus_tcp)
  * [checkmk_mail_relay_host](#checkmk_mail_relay_host)
  * [checkmk_network](#checkmk_network)
  * [checkmk_site_id](#checkmk_site_id)
  * [checkmk_version](#checkmk_version)
* [Dependencies](#dependencies)
* [License](#license)
* [Author](#author)

---

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
  - /var/lib/checkmk:/omd/sites
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
checkmk_version: 1.6.0p19
```

## Dependencies

* [rolehippie.docker](https://github.com/rolehippie/docker)

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
