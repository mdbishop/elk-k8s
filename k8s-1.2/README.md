# Templates for creating ELK stack in Kubernetes

Steps:

1. Create namespace elk first:

      ```
   	kubectl create -f elk
      ```
      
1. Create two service accounts:

      ```
   	kubectl create -f service-account-elk.yml
   	kubectl create -f service-account-es.yml
   	```

1. Create replication controller by order:

   logstash -> logspout -> elasticsearch -> kibana

   So:
      ```
   	kubectl create -f logstash-rc.yml
   	kubectl create -f logstash-svc.yml
   	kubectl create -f logspout-rc.yml
   	kubectl create -f es-rc.yml
   	kubectl create -f es-svc.yml
   	kubectl create -f kibana-rc.yml
   	kubectl create -f kibana-svc.yml
      ```

Tested in K8s 1.3.x.
