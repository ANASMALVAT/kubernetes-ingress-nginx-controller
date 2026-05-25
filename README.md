# kubernetes-ingress-nginx-controller

This repository is a **template for an NGINX Ingress Controller** that you can use in your Kubernetes cluster, whether it is on-premises or on cloud.

## What this template includes

The file [Ingress.nginx.controller.yaml](Ingress.nginx.controller.yaml) is a ready-to-customize Ingress resource that demonstrates how to expose an application through the NGINX Ingress Controller.

### Features included in the manifest

- **Regex-based routing** using `nginx.ingress.kubernetes.io/use-regex` and `rewrite-target`
- **Rate limiting** per client IP using `limit-rps`, `limit-connections`, and `limit-burst-multiplier`
- **Timeouts and buffering** for upstream traffic, including proxy timeouts and body size limits
- **Basic authentication** via `auth-type`, `auth-secret`, and `auth-realm`
- **CORS configuration** for browser-based cross-origin requests
- **Sticky sessions** using cookie-based affinity
- **TLS/HTTPS enforcement** with `ssl-redirect`
- **Backend service routing** to a ClusterIP service named `nginx-clusterip`

## How to use this template

1. Review and update the host names, TLS secret name, and backend service name in [Ingress.nginx.controller.yaml](Ingress.nginx.controller.yaml).
2. Ensure the NGINX Ingress Controller is installed in your cluster.
3. Apply the manifest to your cluster:

```bash
kubectl apply -f Ingress.nginx.controller.yaml
```

## Notes

- The manifest is intended as a **starting point** and should be adjusted to match your application, domain names, and security requirements.
- The auth and custom header sections are included as examples and can be enabled or modified as needed.
