# gophish-k8s

This repo consists of manifests to deploy [gophish](https://github.com/gophish/gophish) into [GKE](https://cloud.google.com/kubernetes-engine?hl=en) with GCE [loadbalancer](https://cloud.google.com/kubernetes-engine/docs/concepts/ingress).

## Create External IP Address

`gcloud compute addresses create external-ip-name --global --project your-gcp-project`

## Create TLS Secret from your SSL Certificate

`kubectl create secret tls yourdomain-com-cert --cert=certificate-fullchain.crt --key=certificate.key -n namespace`

## Create Google Managed Certificate

- Refer to `certificate.yaml` to deploy a google managed certificate and bind it to the ingress
- You need to ensure your DNS is updated with the address, It takes few minutes for the SSL Certificate to fully propagate.

[Read More](https://blog.dhivehi.dev/efficiently-deploying-gophish-on-kubernetes-with-google-cloud-94bcb37ca049)
