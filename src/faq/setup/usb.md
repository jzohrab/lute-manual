# Can I store Lute data on a USB key?

If you regularly switch between computers, one option for setup (which sounds dicey to me :-) ) is to store your data in a USB key.

## Pip

For pip users, you could custom config.yml file, and put it in the root folder where you run Lute, with something like the following:

```
# File config.yml
ENV: prod
DBNAME: lute.db
DATAPATH: /full/path/to/your/usb/lute/folder
BACKUP_PATH: /full/path/to/backup/folder
```

When Lute runs, it uses this config file, and will write all of its data in the folder specified in the DATAPATH.

## Docker

Docker users should change their docker-compose.yml to map the USB key folder to the mounted /lute/data directory.