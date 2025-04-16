This is ansible playbook that deploys 5 nodes cluster (use minimum 3 nodes) using bitnami Docker image in KRaft mode

```ansible-playbook --diff --inventory hosts.yaml playbook-kafka.yaml ```

To completly DESTROY cluster with all data like never exists use this playbook:

```ansible-playbook --diff --inventory hosts.yaml playbook-destroy.yaml ```
