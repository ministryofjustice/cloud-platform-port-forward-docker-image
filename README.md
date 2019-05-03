# Non-root port forwarding for Docker

Based on [marcnuri/port-forward](https://hub.docker.com/r/marcnuri/port-forward)

This image uses `socat` to forward network traffic as defined by the environment variables.

It runs as a non-root user, in order to comply with the [Pod Security Policy][psp]
in the [Ministry of Justice Cloud Platform][moj-cp]

[psp]: https://kubernetes.io/docs/concepts/policy/pod-security-policy/
[moj-cp]: https://github.com/ministryofjustice/cloud-platform

## Usage

Define the following environment variables to configure port-forwarding.

Variable | Description | Optional
-------- | ----------- | --------
REMOTE_HOST | IP or address of the host you want to forward traffic to | no
REMOTE_PORT | Port on remote host to forward traffic to | yes (8000)
LOCAL_PORT | Port where container listens. Must be **non-privileged** (i.e. >1024) | yes (8000)

## Docker hub

Docker image hosted at Docker Hub: [ministryofjustice/port-forward](https://hub.docker.com/r/ministryofjustice/port-forward/)
