# ansible-role-foundryvtt-docker #

[![GitHub Build Status](https://github.com/felddy/ansible-role-foundryvtt-docker/workflows/build/badge.svg)](https://github.com/felddy/ansible-role-foundryvtt-docker/actions)
[![Total alerts](https://img.shields.io/lgtm/alerts/g/felddy/ansible-role-foundryvtt-docker.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/felddy/ansible-role-foundryvtt-docker/alerts/)
[![Language grade: Python](https://img.shields.io/lgtm/grade/python/g/felddy/ansible-role-foundryvtt-docker.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/felddy/ansible-role-foundryvtt-docker/context:python)

This Ansible role will install the FoundryVTT docker container from: [felddy/foundryvtt-docker](https://github.com/felddy/foundryvtt-docker).

## Requirements ##

None.

## Role Variables ##

### Required ###

| Name             | Purpose  |
|------------------|----------|
| foundry_username | Account username or email address for foundryvtt.com.  Required for downloading an application release. |
| foundry_password | Account password for foundryvtt.com.  Required for downloading an application release. |

### Optional ###

| Name  | Purpose |
|-------|---------|
| foundry_admin_key | Admin password to be applied at startup.  If omitted the admin password will be cleared. |
| foundry_aws_config | An absolute or relative path that points to the [awsConfig.json](https://foundryvtt.com/article/aws-s3/) or `true` for AWS environment variable [credentials evaluation](https://docs.aws.amazon.com/sdk-for-javascript/v2/developer-guide/setting-credentials-node.html) usage. |
| foundry_version | Version of Foundry Virtual Tabletop to install. |
| foundry_world | The world to startup at system start. |

## Dependencies ##

- [`ansible-role-docker`](https://github.com/cisagov/ansible-role-docker)

## Example Playbook ##

Here's how to use it in a playbook:

```yaml
- hosts: all
  become: yes
  become_method: sudo
  vars:
    foundry_username: <your_username>
    foundry_password: <your_password>
  roles:
    - ansible-role-foundryvtt-docker
```

## Contributing ##

We welcome contributions!  Please see [here](CONTRIBUTING.md) for
details.

## License ##

This project is in the worldwide [public domain](LICENSE).

This project is in the public domain within the United States, and
copyright and related rights in the work worldwide are waived through
the [CC0 1.0 Universal public domain
dedication](https://creativecommons.org/publicdomain/zero/1.0/).

All contributions to this project will be released under the CC0
dedication. By submitting a pull request, you are agreeing to comply
with this waiver of copyright interest.
