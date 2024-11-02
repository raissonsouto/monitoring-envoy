# Monitoring Envoy

This repository provides instructions and configurations for monitoring Envoy using Graphite and Grafana in Docker and Kubernetes environments.

## Run demo in Docker

To run the demo in Docker, use the following command:

```
cd docker
docker compose up -d
```

## Run demo in Kubernetes

To run the demo in Kubernetes, apply the configurations from the k8s directory:

```
kubectl apply -f k8s
```

## Access Grafana

Once deployed, you can access Grafana to visualize metrics. Grafana can typically be accessed at http://localhost:3000 if running locally at docker, or through the appropriate endpoint in your setup.

## Test

To test connectivity and monitor requests per second to the nginx, you can use the following Bash command:

```
while true; do curl -s "address" > /dev/null; sleep 1; done
```

Replace "address" with the actual URL or IP address you want to test against (e.g. 127.0.0.1:10000). This command will make a silent curl request to the specified address every second.