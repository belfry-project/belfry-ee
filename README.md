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

## Pinned inputs

`execution-environment.yml` pins its inputs so that a build is reproducible: the AlmaLinux base image by digest (a `dnf -y upgrade --refresh` step still adds the security updates published after it), the Galaxy collections to exact versions, and awxkit to the wheel of the latest Belfry release. Renovate (`renovate.json`) proposes updates for all of them.
