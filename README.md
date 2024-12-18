# MicroK8s profile

## Ansible

### How to run

First of all, edit inventory file for your specific infrastructure, then run:

`ansible-playbook -i ansible_microk8s/inventory ansible_microk8s/microk8s-cluster.yml`

### Addons

You can add/remove addons in the playbook file. For list of available addons, see `ansible_microk8s/roles/microk8s-cluster/defaults/main.yml` or visit microk8s addons documentation.

## Services

### Portianer

Portainer accessible at http://10.88.99.1:30777/

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

or try this one:

```
eyJhbGciOiJSUzI1NiIsImtpZCI6IjZNQjBHdHhlSlFJU2ZwOGRHbHczUi1lamJnbDB6blp5VWJ0dWV4UTF5VVEifQ.eyJpc3MiOiJrdWJlcm5ldGVzL3NlcnZpY2VhY2NvdW50Iiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9uYW1lc3BhY2UiOiJrdWJlLXN5c3RlbSIsImt1YmVybmV0ZXMuaW8vc2VydmljZWFjY291bnQvc2VjcmV0Lm5hbWUiOiJkZWZhdWx0LXRva2VuLXdmd2ZoIiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9zZXJ2aWNlLWFjY291bnQubmFtZSI6ImRlZmF1bHQiLCJrdWJlcm5ldGVzLmlvL3NlcnZpY2VhY2NvdW50L3NlcnZpY2UtYWNjb3VudC51aWQiOiI3YTk0OTNiMS01ZDljLTRkY2UtYjA0My1hNGEzZjdmODE0MzUiLCJzdWIiOiJzeXN0ZW06c2VydmljZWFjY291bnQ6a3ViZS1zeXN0ZW06ZGVmYXVsdCJ9.J4oAHkjfBmx67C5fNgorwHmjN0jnAkfG-Qzc8qryxqJx4QdSs4A9-2BabFyCEA02dcHcfKiTNtqQG2_6Av3vOIqkU92DLoGavwF_JY4x9_JqtbBl0BBcO2Y5P2D5cJ15Vx-2uuqnaGgPyO8RJ6aygB4bws42xXG1websMityeLaHv8SPiD805ppP12wQQ-EoQj8PfRVh7i6prcTsntxlEaIfbQ3ngzNi4lhTysFJBbJamjj7TKb6LC9P6zxWjsXwMOObyNXPKLXUtW1TGm8rJKhwENKt37nn2fpRZYi_otx2x1C4Ad9fMir7EaXNr2aUug5ZtmRUl9zWGvqHP-8-nw
```

You might need to allow invalid certificates for resources loaded from localhost (visit `chrome://flags/#allow-insecure-localhost` for chrome)

---