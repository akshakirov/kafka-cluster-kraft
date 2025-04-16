This is ansible playbook that deploys 5 nodes cluster (use minimum 3 nodes) using bitnami Docker image in KRaft mode

You just need to change your hosts.yaml  according to your host names   and generate kafka_cluster_id

```cat /proc/sys/kernel/random/uuid | tr -d '-' | base64 | cut -b 1-22```

add ```kafka_topics``` in hosts.yaml


and run a playbook

```ansible-playbook --diff --inventory hosts.yaml playbook-kafka.yaml ```



Now you can use nodes of your cluster in application

kafka-n1.test.com:9092
kafka-n2.test.com:9092
kafka-n3.test.com:9092
kafka-n4.test.com:9092
kafka-n5.test.com:9092

Other stuff that included:
http://kafka.test.com - UI Kafka
http://kafka.test.com:9308/metrics - kafka-exporter
http://kafka-n1.test.com:9404/metrics - jmx_prometheus exporter
http://kafka-n2.test.com:9404/metrics - jmx_prometheus exporter
http://kafka-n3.test.com:9404/metrics - jmx_prometheus exporter
http://kafka-n4.test.com:9404/metrics - jmx_prometheus exporter
http://kafka-n5.test.com:9404/metrics - jmx_prometheus exporter

To completly DESTROY cluster with all data like never exists use this playbook:

```ansible-playbook --diff --inventory hosts.yaml playbook-destroy.yaml ```
