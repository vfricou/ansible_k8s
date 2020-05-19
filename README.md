# README

## Prerequisite

- Firewall disable or fully configured for Kubernetes service [Kubernetes documentation](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/install-kubeadm/#check-required-ports)

## Tags

| Tag          | Description                                                               |
| ------------ | ------------------------------------------------------------------------- |
| check_target | Query remote target os and hardware to check os and hardware requirements |

## Variables

| Variable | Default value | Description |
| - | - | - |
| d_calico_version | 3.14 | Calico chart version to deploy |
| d_perform_action | configure | Determine if kubernetes packages should be installed/updated if actions set to "install" |
| d_k8s_prim_master_addr | 192.168.56.20 | Set k8s master advertisement address |
| d_k8s_pods_network | 192.168.0.0/16 | Set k8s pods network ranges |

## Usage

### Install from scratch

```bash
ansible-playbook -i inventory kubernetes.yml -e "d_perform_action=install"
```

### Example

#### With different pod network
```bash
ansible-playbook -i inventory kubernetes.yml -e "d_perform_action=install d_k8s_pods_network=172.16.0.0/16"
```