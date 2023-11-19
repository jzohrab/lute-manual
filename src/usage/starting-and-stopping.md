# Starting and stopping

These scripts are on a Mac; Linux will be the same, Windows slightly different.  They're rough guides only, your system may vary.

* [Python/pip](#if-using-pip)
* [Docker](#if-using-docker)
* [Source](#if-you-installed-from-source)

## If using pip

Assuming you're using venv:

```
cd ~/my_lute

# Activate the virtual environment
source myenv/bin/activate

# Start
python -m lute.main

# ... Open your web browser to http://localhost:5000.
# When done, hit Ctl-C to stop

deactivate
```

### Python/pip startup options

The python `lute.main` defaults for Lute startup will hopefully be
fine for most people, but some things can be customized.

```
$ python -m lute.main --help
usage: main.py [-h] [--port PORT] [--config CONFIG]

Start lute.

optional arguments:
  -h, --help       show this help message and exit
  --port PORT      Port number (default: 5000)
  --config CONFIG  Path to override config file. Uses lute/config/config.yml if not set.
```

With the `--config` option, you can pass the path to a new config file
to customize the folder where Lute stores data (and a few other
things, if needed).  Copy the
[config.yml.example](https://raw.githubusercontent.com/jzohrab/lute-v3/master/lute/config/config.yml.example)
to a new file in your Lute folder, edit and save it, and pass its path
when calling `lute.main`:

```
python -m lute.main --config ./my_personal_config.yml
```

If your custom config file is named `config.yml` and it's in the same folder where you call `lute.main`, Lute will use that by default; i.e., the following are equivalent

```
python -m lute.main --config ./config.yml
python -m lute.main
```


## If using Docker

Assuming you have your docker compose set up:

```
cd ~/my_lute_docker

# Run it:
docker compose up

# ... Open your web browser to http://localhost:5000.
# When done, hit Ctl-C to stop
```

You can also run it as a background job:

```
docker compose up -d
# ... use Lute, then to stop it:
docker compose down
```

## If you installed from source

```
cd ~/my_lute_source
source .venv/bin/activate
inv start   # or "python -m lute.main"
# ... etc.
# Ctl-C when done.
deactivate
```