# Lab 2

We now start with Lab 5. The pre-requisites remain the same as for Lab 1.

This lab will cover instrumenting and observing K8 and applications on K8.

---
### K8s Monitoring.

We will be using the same Elastic Cloud instance provisioned earlier.

1. Minikube Setup.
2. Helm Setup
3. Kube State Metrics Setup.
4. Login to your Elastic Cloud Instance and navigate to Integrations.
5. Elastic Agent setup on Minikube.

---
### Otel Demo App on Minikube.

1. Setup secrets on K8.
   ```bash
      kubectl create secret generic elastic-secret --from-literal=elastic_apm_endpoint='YOUR_APM_ENDPOINT_WITHOUT_HTTPS_PREFIX' --from-literal=elastic_apm_secret_token='YOUR_APM_SECRET_TOKEN'
   ```
2. Clone the Demo Repo.
   ```bash
      mkdir lab5/k8-monitoring
      cd lab5/k8-monitoring
      git clone https://github.com/elastic/opentelemetry-demo
      cd opentelemetry-demo
   ```
3. Execute following steps to deploy app to minikube.
   ```bash
      # switch to the kubernetes/elastic-helm directory
      cd kubernetes/elastic-helm

      # add the open-telemetry Helm repostiroy
      helm repo add open-telemetry https://open-telemetry.github.io/opentelemetry-helm-charts

      # deploy the demo through helm install
      helm install -f values.yaml my-otel-demo open-telemetry/opentelemetry-demo

   ```
4. To access the application run the following command.
   ```bash
      kubectl port-forward svc/my-otel-demo-frontendproxy 8080:8080 --address='0.0.0.0'
   ```
   Once the application starts running, access the URL with the FQDN or IP address of the lab machine at port 8080.
   
   http://lab-machine-fqdn-or-url:8080/
>                        End Of Lab 5.


