<div align="center">
<h1>RenderCV</h1>

_Resume builder for academics and engineers, deployed at [rendercv.com](https://rendercv.com)_

[![test](https://github.com/rendercv/rendercv/actions/workflows/test.yaml/badge.svg?branch=main)](https://github.com/rendercv/rendercv/actions/workflows/test.yaml)
[![coverage](https://coverage-badge.samuelcolvin.workers.dev/rendercv/rendercv.svg)](https://coverage-badge.samuelcolvin.workers.dev/redirect/rendercv/rendercv)
[![docs](<https://img.shields.io/badge/docs-mkdocs-rgb(0%2C79%2C144)>)](https://docs.rendercv.com)
[![pypi-version](<https://img.shields.io/pypi/v/rendercv?label=PyPI%20version&color=rgb(0%2C79%2C144)>)](https://pypi.python.org/pypi/rendercv)
[![pypi-downloads](<https://img.shields.io/pepy/dt/rendercv?label=PyPI%20downloads&color=rgb(0%2C%2079%2C%20144)>)](https://pypistats.org/packages/rendercv)

</div>

- Go to https://rendercv.com/ and create your CV
- Press `Download all data` to download all config files to your computer
- Place your photo (named `profile_picture.png`) at the same level as config
  files
- Build docker image using command
```shell
git clone https://github.com/Haevnen/rendercv.git
cd rendercv
docker build --no-cache -t rendercv-local .
```
- Run this command to generate CV in pdf
```bash
docker run --rm -v "$PWD":/work -u "$(id -u):$(id -g)" -e HOME=/tmp -w /work rendercv-local render cv.yaml --dont-generate-markdown --dont-generate-html --dont-generate-png --design design.yaml
```