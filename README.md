# Belfry EE

The default Execution Environment for [Belfry](https://github.com/belfry-project/belfry), published as `ghcr.io/belfry-project/belfry-ee` (tags `latest`, `main` and `main-<sha>`).

It is a continuation of [AWX EE](https://github.com/ansible/awx-ee), the default Execution Environment for AWX. Inside Belfry it keeps the managed name "AWX EE (latest)", so existing job templates keep working.

AWX and Ansible are trademarks of Red Hat, Inc. Belfry is not affiliated with or endorsed by Red Hat, Inc.

## Build the image locally

First, [install ansible-builder](https://ansible-builder.readthedocs.io/en/stable/installation/).

Then run the following command from the root of this repo:

```bash
$ ansible-builder build -v3 -t ghcr.io/belfry-project/belfry-ee # --container-runtime=docker # Is podman by default
```
