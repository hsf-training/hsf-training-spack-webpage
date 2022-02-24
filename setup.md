---
title: Setup
---
In order to work through this tutorial, you will need access to a Linux system. While
Spack can be used on other operating systems, the tutorial is focused on Linux systems.

On your computer, you need to have:
* `git`
* Python, either 2.8+ or 3.5+
* C/C++ compiler, the system default is fine on most recent systems.

If you do not have access to a Linux system, you can use a [Docker][] image.

## [Docker][] based setup

[Docker][] is a powerful tool that allows you to perform a virtualization of your
environment but completely in software.  It allows you to bundle up the installation of
tools for use by others in a uniform way without changing your underlying system, and
works on all major OS's (latest Windows 10 Update _highly_ recommended, and required
if you have Windows 10 Home).

### Setup: Ephemeral

A quick and minimal docker:

```bash
docker run --rm -it alpine
apk add git g++ cmake make
```

This does *not* make a volume, so you will lose whatever you do in here when it exits.

### Setup: Persistent

This will allow you to keep your changes, which is both good (if you want to revisit them) and bad
(if you want to know exactly what went into making them).

```bash
docker run -v $PWD:/work --rm -it alpine
apk add g++ cmake make
cd /work
```

The folder on your computer and docker folder are linked. Permissions/users will come from the
docker container.

{% include links.md %}
