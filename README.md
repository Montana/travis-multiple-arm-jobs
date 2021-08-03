# travis-multiple-arm-jobs
Travis CI using multiple jobs using ARM as the main `arch`.

```yaml
arch: arm64
language: generic

env:
- BUILD=MONTANA
- BUILD=MONTANA2
- BUILD=MONTANA3

install: skip

script:
- uname -a
- grep ^processor /proc/cpuinfo
- free -m
- df -h
- df -Th

- sudo snap install core || true
- sudo snap install core
- sudo snap install hello-world
- hello-world

- docker info
- docker run hello-world
```

# TODO 

May remove Docker.
