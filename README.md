# OpenShift Days Roadshow Automation

Ansible collections for OpenShift Days Workshop tracks.

## Collections

- **ops_track** (`openshift_days.ops_track`) - Ops Track Workshop roles
- **dev_track** (`openshift_days.dev_track`) - Dev Track Workshop roles

## Installation

```yaml
# In requirements.yml
collections:
  - name: git+https://github.com/rhpds/openshift-days-roadshow-automation.git#/ops_track
    type: git
    version: main
  - name: git+https://github.com/rhpds/openshift-days-roadshow-automation.git#/dev_track
    type: git
    version: main
```

## License

GPL-2.0-or-later
