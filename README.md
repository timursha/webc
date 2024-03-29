# yq 

[![Build Status](https://travis-ci.org/mikefarah/yq.svg?branch=master)](https://travis-ci.org/mikefarah/yq)  ![Docker Pulls](https://img.shields.io/docker/pulls/mikefarah/yq.svg) ![Github Releases (by Release)](https://img.shields.io/github/downloads/mikefarah/yq/total.svg)


a lightweight and portable command-line YAML processor

The aim of the project is to be the [jq](https://github.com/stedolan/jq) or sed of yaml files.

## Install
On MacOS:
```
brew install yq
```
On Ubuntu and other Linux distros supporting `snap` packages:
```
snap install yq
```
On Ubuntu 16.04 or higher from Debian package:
```
sudo add-apt-repository ppa:rmescandon/yq
sudo apt update
sudo apt install yq -y
```
or, [Download latest binary](https://github.com/mikefarah/yq/releases/latest) or alternatively:
```
go get gopkg.in/mikefarah/yq.v2
```

## Run with Docker

Oneshot use:

```bash
docker run -v ${PWD}:/workdir mikefarah/yq yq [flags] <command> FILE...
```

Run commands interactively:

```bash
docker run -it -v ${PWD}:/workdir mikefarah/yq sh
```

## Features
- Written in portable go, so you can download a lovely dependency free binary
- Deep read a yaml file with a given path
- Update a yaml file given a path
- Update a yaml file given a script file
- Update creates any missing entries in the path on the fly
- Create a yaml file given a deep path and value
- Create a yaml file given a script file
- Prefix a path to a yaml file
- Convert from json to yaml
- Convert from yaml to json
- Pipe data in by using '-'
- Merge multiple yaml files where each additional file sets values for missing or null value keys.
- Merge multiple yaml files and override previous values.
- Merge multiple yaml files and append array values.
- Supports multiple documents in a single yaml file

## [Usage](http://mikefarah.github.io/yq/)

Check out the [documentation](http://mikefarah.github.io/yq/) for more detailed and advanced usage.

```
Usage:
  yq [flags]
  yq [command]

Available Commands:
  delete      yq d [--inplace/-i] [--doc/-d index] sample.yaml a.b.c
  help        Help about any command
  merge       yq m [--inplace/-i] [--doc/-d index] [--overwrite/-x] [--append/-a] sample.yaml sample2.yaml
  new         yq n [--script/-s script_file] a.b.c newValue
  read        yq r [--doc/-d index] sample.yaml a.b.c
  write       yq w [--inplace/-i] [--script/-s script_file] [--doc/-d index] sample.yaml a.b.c newValue
  prefix      yq p [--inplace/-i] [--doc/-d index] sample.yaml a.b.c

Flags:
  -h, --help      help for yq
  -t, --trim      trim yaml output (default true)
  -v, --verbose   verbose mode
  -V, --version   Print version information and quit

Use "yq [command] --help" for more information about a command.
```

## Contribute
1. `scripts/devtools.sh`
2. `make [local] vendor`
3. add unit tests
4. apply changes (use govendor with a preference to [gopkg](https://gopkg.in/) for package dependencies)
5. `make [local] build`
6. If required, update the user documentation 
    - Update README.md and/or documentation under the mkdocs folder
    - `make [local] build-docs`
    - browse to docs/index.html and check your changes 
7. profit
# webc
