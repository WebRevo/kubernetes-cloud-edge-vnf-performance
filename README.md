# Kubernetes Cloud vs Edge VNF Performance Evaluation

## Overview
This project evaluates the performance of Kubernetes in cloud-like and edge-like environments using a lightweight Virtual Network Function (VNF) based on an NGINX reverse proxy.

## Environments
- Cloud-like: kind (Kubernetes in Docker)
- Edge-like: k3d (K3s lightweight Kubernetes)

## Architecture
User → NGINX (VNF) → Backend Pods

## Components
- NGINX reverse proxy (load balancer)
- Backend services using http-echo
- Kubernetes Deployments and Services

## Tools Used
- Docker Desktop
- kind
- k3d
- kubectl
- wrk (for load testing)

## Deployment Steps
1. Create cluster (kind / k3d)
2. Deploy backend services
3. Deploy NGINX with ConfigMap
4. Expose services
5. Test using port-forward

## Performance Testing
Traffic generated using wrk:
- Low load: 10 connections
- Medium load: 50 connections
- High load: 100 connections

Metrics collected:
- Latency
- Requests per second
- CPU usage
- Memory usage

## Results Summary
- Both environments performed similarly under low load
- Cloud showed better throughput under higher load
- Edge showed slightly higher latency under heavy traffic
- Kubernetes is suitable for lightweight VNFs at the edge

## Files Included
- nginx.conf
- nginx-deploy.yaml
- backend.yaml
- commands.txt
- GenAI_troubleshooting.md

## Conclusion
Kubernetes provides an effective platform for telecom workloads in both cloud and edge environments, with edge deployments requiring careful resource consideration.