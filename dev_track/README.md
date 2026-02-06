# OpenShift Days: Dev Track Collection

Ansible collection for deploying the OpenShift Days Dev Track Workshop.

## Roles

(Roles to be added)

## Usage

```yaml
- name: Deploy Dev Track Workshop
  hosts: localhost
  tasks:
    - ansible.builtin.include_role:
        name: openshift_days.dev_track.<role_name>
      vars:
        ACTION: create
```

## License

GPL-2.0-or-later
