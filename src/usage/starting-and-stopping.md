# Starting and stopping

These scripts are on a Mac; Linux will be the same, Windows slightly different.  They're rough guides only, your system may vary.

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

## If using Docker

Assuming you have your docker compose set up:

```
cd ~/my_lute_docker

# Run it:
docker compose up

# ... Open your web browser to http://localhost:5000.
# When done, hit Ctl-C to stop
```

## If you installed from source

```
cd ~/my_lute_source
source .venv/bin/activate
inv start
# ... etc.
# Ctl-C when done.
deactivate
```