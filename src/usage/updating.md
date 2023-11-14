# Updating Lute

First, you **must [stop Lute](./usage/starting-and-stopping.md)**.

(Lute or Python may lock certain files while running, shutting down ensures that things will update safely.)

Then:

## ... if using pip

```
cd /path/to/your/lute    # change this line. :-)
pip install --upgrade lute3
```

## ... if using Docker

This assumes you're using a `docker-compose.yml` file.

```
cd /path/to/your/lute    # change this line. :-)
docker compose pull
docker compose up -d --remove-orphans
```

## ... if using source

`git fetch` etc etc.  (I assume you know what you're doing here.)