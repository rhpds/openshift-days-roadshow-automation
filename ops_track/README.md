# OpenShift Days: Ops Track Collection

Ansible collection for deploying the OpenShift Days Ops Track Workshop.

## Roles

### Workshop Core
- `ocp4_workload_days_ops_track` - Workshop orchestrator: kubeconfig setup, cluster metadata extraction, diagnostics, Showroom configuration (patches deployment with workshop variables, rebuilds Antora site, CLI tools setup)
- `ocp4_workload_cluster_diagnostics` - End-of-deployment comprehensive cluster diagnostics (operator status, pod health, storage, networking)
- `ocp4_workload_kubernetes_image_puller` - Pre-pull workshop container images to nodes

### RHACS (Advanced Cluster Security)
- `ocp4_workload_rhacs` - Original ops_track copy with hardcoded resource reductions (deprecated, kept for reference)
- `ocp4_workload_rhacs_v2` - Variable-driven version with optional resource overrides. Behaves identically to the upstream `core_workloads` role when no overrides are set. Upstream PR pending: https://github.com/agnosticd/core_workloads/pull/76

### Quay (Container Registry)
- `ocp4_workload_quay_operator` - Original ops_track copy with hardcoded resource reductions (deprecated, kept for reference)
- `ocp4_workload_quay_operator_v2` - Variable-driven version with optional resource/replica overrides and startup probe patch. Behaves identically to the upstream `core_workloads` role when no overrides are set. Upstream PR pending: https://github.com/agnosticd/core_workloads/pull/76

> **Note:** The v2 roles exist temporarily while the upstream core_workloads PR is under review. Once merged, the v2 copies and the original ops_track copies will be removed and the workshop will use the upstream roles directly with override variables set in agnosticv.

### Multi-Cluster & ACM
- `ocp4_workload_rhacm_cloud_credentials` - ACM cloud credentials for KubeVirt provider
- `ocp4_workload_acm_multicluster_observability` - ACM multi-cluster observability
- `ocp4_workload_hcp_kubevirt` - Hosted Control Planes on KubeVirt
- `ocp4_workload_create_hcp_cluster` - Pre-provision a managed HCP cluster

### Day 2 Operations
- `ocp4_days_workload_compliance_operator` - Compliance Operator installation
- `ocp4_workload_oadp` - OADP Backup/Restore operator

### Developer Experience
- `ocp4_days_workload_rhdh` - Red Hat Developer Hub (simplified deployment)

### Temporary Copies (from upstream core_workloads)
These are unmodified copies of upstream roles that were needed when upstream had issues. They should be removed once no longer required.
- `ocp4_workload_metallb_temp`
- `ocp4_workload_openshift_gitops_temp`
- `ocp4_workload_openshift_virtualization_temp`
- `ocp4_workload_pipelines_temp`
- `ocp4_workload_rhacm_temp`
- `ocp4_workload_web_terminal_temp`

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
