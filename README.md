# Free-Threaded Python Docker Image

This is a minimal clone of the official Python Docker image with **free-threading enabled** (`--disable-gil`).

## What’s Different?

Literally just one thing:  
In the CPython build step, I've added this flag:
```
–disable-gil
```
Everything else is the same as the official image.

## Why?

Free-threading (aka “no-GIL”) is experimental in Python 3.13+. If you want to try running Python with GIL disabled in a container, this image gives you a head start.

## How to Build Your Own

If you don’t trust random images from the internet (you shouldn’t), you can build it yourself:

1. Start from the official Python Dockerfile (e.g., https://github.com/docker-library/python)
2. Add `--disable-gil` to the `./configure` step during CPython build
3. Done.

## Quick Start


```sh
docker pull ghcr.io/abebus/free-threaded-python-docker-image:main
```


## Warning

This is experimental. Things may break. Performance may vary. Use at your own risk.

---

Built on top of: https://github.com/docker-library/python
 