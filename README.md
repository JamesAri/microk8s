# MicroK8s profile

## Ansible

### How to run

First of all, edit inventory file for your specific infrastructure, then run:

`ansible-playbook -i ansible_microk8s/inventory ansible_microk8s/microk8s-cluster.yml`

### Addons

You can add/remove addons in the playbook file. For list of available addons, see `ansible_microk8s/roles/microk8s-cluster/defaults/main.yml` or visit microk8s addons documentation.

## Services

### Portianer

Portainer accessible at `http://<master_node_ip>:30777/`

login: admin<br>
password: *same as for rpi authentication*

---

### Nginx (testing deployment)

Nginx accessible at `http://<node_ip>:32237/`

---

### Kubernetes Dashboard
Create ssh tunnel:

```
ssh -L 8001:127.0.0.1:31308 admin@pi1
```

then visit https://localhost:8001/

On the login page, select authentication via token. You might need to generate a new one (see https://microk8s.io/docs/addon-dashboard)

You might need to allow invalid certificates for resources loaded from localhost (visit `chrome://flags/#allow-insecure-localhost` for chrome)

---
