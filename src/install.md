# Installation

There are currently three different methods to install Lute v3 on your system, with different system requirements:

* [Python package install using `pip`](install.md#using-pip)
* [Docker](install.md#using-docker)
* [From source](install.md#from-source)

> I can't recommend any particular installation method: they all have trade offs.  My personal preference is to install using pip.

## Using pip

System requirements:

* Python 3.8+ and pip
* Japanese learners will also need to [install MeCab](./mecab.md)

Lute can be installed from [https://pypi.org/project/lute3/](https://pypi.org/project/lute3/).  Here's a summary of the instructions on that pypi page (Linux/Mac, Windows will be similar).  Note my system has python3.8, your system may vary:

```
python3.8 -m venv myenv
source myenv/bin/activate

# Install
pip install --upgrade lute3

# Start
python -m lute.main

# Open your web browser to http://localhost:5000
# When done, hit Ctl-C

deactivate
```

## Using Docker

System requirements:

* Docker

> Docker is a containerization platform that allows you to run applications in a sandboxed environment (ref the [Docker documentation](https://docs.docker.com/)).  **Docker is not available or is problematic on some systems, particularly Windows.**

Lute has a pre-built docker image at [https://hub.docker.com/r/jzohrab/lute3](https://hub.docker.com/r/jzohrab/lute3).  There are notes on that page about the image.  Here's one way to get started using a `docker-compose.yml` file:

* create a folder on your system for your lute, with folders for the data and backups, e.g.:

```
- my_lute/
    docker-compose.yml
    - data/
    - backups/
```

* Put the following in the `docker-compose.yml`:

```
version: '3.9'
services:
  lute:
    image: jzohrab/lute3:latest
    ports:
      - 5000:5000
    volumes:
      - ./data:/lute_data
      - ./backups:/lute_backup
```

* open a terminal/shell in the `my_lute` folder, and start Lute:

```
docker compose up
```

## From source

Developers and gearheads can install Lute from source: see the [Lute repository](https://github.com/jzohrab/lute-v3/blob/master/docs/development.md).

If you want to develop Lute, you'll also need to [install MeCab](./mecab.md).
