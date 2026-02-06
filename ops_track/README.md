# OpenShift Days: Ops Track Collection

Ansible collection for deploying the OpenShift Days Ops Track Workshop.

## Roles

- `ocp4_workload_days_ops_track` - Workshop setup and cluster diagnostics
- `ocp4_days_workload_compliance_operator` - Compliance Operator installation
- `ocp4_days_workload_rhdh` - Red Hat Developer Hub (simplified)
- `ocp4_days_workload_ols` - OpenShift Lightspeed
- `ocp4_workload_oadp` - OADP Backup/Restore
- `ocp4_workload_kubernetes_image_puller` - Pre-pull workshop images
- `ocp4_workload_rhacm_cloud_credentials` - ACM cloud credentials
- `ocp4_workload_acm_multicluster_observability` - ACM observability
- `ocp4_workload_hcp_kubevirt` - Hosted Control Planes on KubeVirt

## Usage

```yaml
- name: Deploy Ops Track Workshop
  hosts: localhost
  tasks:
    - ansible.builtin.include_role:
        name: openshift_days.ops_track.ocp4_workload_days_ops_track
      vars:
        ACTION: create
```

## License

GPL-2.0-or-later
