# Installation

There are currently three different methods to install Lute v3 on your system, with different system requirements:

* [Python package install using `pip`](install.md#using-pip)
* [Docker](install.md#using-docker)
* [From source](install.md#from-source)

I can't recommend any particular installation method: they all have trade offs.  My personal preference is to install using pip.  If you're studying Japanese and your system supports Docker, I'd recommend using Docker as it the lute3 image includes some other needed dependencies.

## Using pip

### System requirements:

* Python 3.8+ and pip
* Japanese learners will also need to [install MeCab](./mecab.md)

Lute can be installed from [https://pypi.org/project/lute3/](https://pypi.org/project/lute3/).  Here's a summary of the instructions on that pypi page (Linux/Mac, Windows will be similar).

> * Before starting, make sure you have python 3.8+ installed!  Run `python3 --version` from the terminal to check.

* Create a Lute folder
```
mkdir -p ~/my_lute
cd ~/my_lute
```

* Set up virtual environment.  If this line gives an error, see the notes above.
```
python3 -m venv myenv
source myenv/bin/activate
```

* Install
```
pip install --upgrade lute3
```

* Start.
```
python -m lute.main
```

> ... Open your web browser to http://localhost:5000.
> Leave this terminal open while you're using Lute.
> When done, hit Ctl-C to deactivate

* You can start lute on a different port if needed:

```
python -m lute.main --port 9876
```


## Using Docker

### System requirements:

* Docker

> Docker is a containerization platform that allows you to run applications in a sandboxed environment (ref the [Docker documentation](https://docs.docker.com/)).  **Docker is not available or is problematic on some systems, particularly Windows.**

Lute has a pre-built docker image at [https://hub.docker.com/r/jzohrab/lute3](https://hub.docker.com/r/jzohrab/lute3).  There are notes on that page about the image.

#### Here's one way to get started using a `docker-compose.yml` file (again a Linux/Mac script):

* Create Lute folders
```
mkdir -p ~/my_lute_docker
cd ~/my_lute_docker
```
* create some subfolders (These subfolders will be mounted to the container)
```
mkdir data
mkdir backups
```

* create a file and name it `docker-compose.yml`, then copy this into it:
```
cat > docker-compose.yml <<EOF
version: '3.9'
services:
  lute:
    image: jzohrab/lute3:latest
    ports:
      - 5000:5000
    volumes:
      - ./data:/lute_data
      - ./backups:/lute_backup
EOF
```

* Run it:
```
docker compose up
```

As with the `pip` installation, you can change the port if your machine is already using port 5000, e.g.:


```
...
    ports:
      - 9876:5000
...
```

## From source

Developers and gearheads can install Lute from source: see the [Lute repository](https://github.com/jzohrab/lute-v3/blob/master/docs/development.md).

If you want to develop Lute, you'll also need to [install MeCab](./mecab.md).
