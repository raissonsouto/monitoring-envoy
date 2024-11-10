# Monitoring Envoy

This repository provides instructions and configurations for monitoring Envoy using Graphite and Grafana in Docker and Kubernetes environments.

## Summary

- [Architecture](#architecture)
- [Setup demo in Docker](#setup-demo-in-docker)
- [Setup demo in Kubernetes](#setup-demo-in-kubernetes)
- [Test it](#test-it)

## Architecture

<img src="https://github.com/raissonsouto/monitoring-envoy/raw/refs/heads/main/diagram.png" alt="diagram" width="700"/>

## Setup demo in Docker

To run the demo in Docker, use the following commands:

```
cd docker
docker compose up -d
```

To end the demo, execute:

```
docker compose down
```

## Setup demo in Kubernetes

To run the demo in Kubernetes, apply the configurations at the k8s directory:

```
kubectl apply -f k8s
```

To end the demo, execute:

```
kubectl delete -f k8s
```

## Test it

To test connectivity and monitor requests per second to the nginx, you can use the following bash command:

```
while true; do curl -s 127.0.0.1:10000 > /dev/null; echo "request made"; sleep 1; done
```

This command will make a silent curl request to the specified address every second. Replace "address" with the actual URL or IP address you want to test against (e.g. 127.0.0.1:10000). You can access Grafana to visualize metrics. Grafana can typically be accessed at http://localhost:3000 if running locally at docker, or through the appropriate endpoint in your k8s setup.

**Obs:** default Grafana user and password is "admin".
