# Ansible workstation self-setup

## Prerequisites

* Installed system (tested with Fedora 38)
* Created user with `sudo` access
* Installed dependencies by running `./bootstrap.sh` script:

  ```shell
  ./bootstrap.sh
  ```

* Create `extra vars` from template eg.:
  
  > Fill in your user details. You can also provide your own templates.

  ```
  cp extra_vars/username-template.yml extra_vars/$USER.yml
  ```

## Usage

```bash
ansible-playbook --ask-become-pass --extra-vars @extra_vars/$USER.yml workstation-setup-eft.yml
```

Currently, the default and tested usage is self-setup of the workstation on
localhost.

## Playbooks

Currently available playbooks are:

* `workstation-setup-eft.yml`
  - includes `worstation-setup-base.yml` playbook
  - adds roles suitable for embedded developer on top of it

## Packages

Currently packages are distributed into 3 groups:

* `packages_base` - suitable for every developer

* `packages_embedded` - especially useful for embedded developers

* `packages_extra_*` - user-specific packages
