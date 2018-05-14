# role-pam

Ansible role to configure PAM (Pluggable Authentication Module).

The role is fully generic and supports all the PAM settings.

## Requirements

The role requires RHEL/CentOS 7 to work.

## Role Variables

The variables are fully documented in the [default configuration](defaults/main.yml) file, including their default values and some examples. This file contains all the settings that can be configured.

Please refer to the default configuration file for the full list and use Linux man pages if you need more information on PAM.

Here is a brief summary of the role's variables:

| Variable                  | Default                  | Description                                       |
| :---                      | :---                     | :---                                              |
| `pam_version`             | `''`                     | PAM version to install.                           |
| `oddjob_version`          | `''`                     | OddJob version to install.                        |
| `pam_base_dir`            | `'/etc/pam.d'`           | Base directory for pam configuration.             |
| `pam_additional_packages` | `[]`                     | List of additional packages to install together with PAM
| `pam_safety_enabled`      | `present`                | If set to present, it will create a safety copy-and-replace of the configuration |
| `pam_safe_file`           | `/etc/pam.d-safe.tar.gz` | Name of the backup file.                          |
| `pam_applications`        | `[]`                     | Configuration for the various application files.  |

## Example Playbook

Using the role without any specific configuration is very simple:

```Yaml
- hosts: servers
  roles:
   - role: pam
```

## License

MIT

## Author Information

[Fabrizio Colonna](colofabrix@tin.it)

## Contributors

Pull requests are also very welcome. Please create a topic branch for your proposed changes. If you don't, this will create conflicts in your fork after the merge.
