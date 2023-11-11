# Restoring backups

As you use Lute more and more, you're building up a ton of valuable data!  It would *really suck* to lose that.

> I'm hoping that you have configured backups in your Settings, and that you are periodically backing up.  If you're not using Lute's built-in backup methods, **please take time to set up some kind of backup.**  All you need to do is copy your `data` file to some location and zip it -- that will back up your database and images.

Restoring backups are as simple as replacing your Lute database with one of your unzipped backups, and restoring your image folder as well.

## Database restores

> To find the directory where your database is, start Lute and go to About > Version and Software Info.  It's the "Data path" line. (**Docker users:** use the data directory you mounted for the container.)

Summary: you replace your database with an unzipped and renamed db backup.  Here's one way to do that:

1. Copy a db backup that you want to restore from your backup directory to the "data path" directory.  For example, after this step, I might have `lute/data/lute_backup_2023-10-04_022616.db.gz`.
1. **Stop Lute.**
2. Browse to that "Data path" directory on your machine, and rename the file `lute.db` to `old_lute.db` (the exact name you pick doesn't matter -- this is just in case your restore goes wrong)
3. Unzip your backup from step 1, and rename it to `lute.db`.  Your data folder should now contain `old_lute.db` and `lute.db`
4. Start Lute, and refresh the browser.  Lute is now connected to your restored backup db.
5. You can either get rid of the `old_lute.db`, or move it somewhere else if you want to keep it.

## Image restores

> The images directory is the same as the database directory.

Summary: copy files!

Your backup images are stored in your backup directory, in `userimages_backup`.  Copy the contents of that directory to the `userimages` directory of your "Data path" directory.

# Test your backups!

It's a good idea to periodically check your backups to ensure that they're good.

## Checking database backupa

First obvious thing to check is the backup file size -- if it's way too small, that's no good.

### Check using queries

You can query the backup database just to validate that the data is present.  Unzip one of your backups, and use Sqlite to connect to it and run queries.

For example, in my backup folder, I have `lute_backup_2023-10-04_022616.db.gz`.  I can unzip this somewhere as `lute_backup_2023-10-04_022616.db` and then try some queries:

```
sqlite3 lute_backup_2023-10-04_022616.db

SQLite version 3.39.5 2022-10-14 20:58:05
Enter ".help" for usage hints.
sqlite> select count(*) from words;     # <-- this is my query
51839
```
That's about right.

### Check using Lute itself (replace your current DB with a backup and verify)

Another option is to temporarily replace your current `lute.db` with one of your backups.  You could follow the steps you did for the database restore, but as a final step rename your `old_lute.db` to `lute.db` again.

## Checking image backup

You can check the `userimages_backup` folder in your designated backup folder to see if your images are there.  Just check the dates of the last handful of files.

On a Mac (and perhaps on Linux systems), you could also use terminal.  E.g. on my Mac, I can check the latest files:

```
ls -larth ~/Dropbox/LuteBackup/userimages_backup/1  | tail -n 20
...
-rw-r--r--@    1 jeff  staff    15K 18 Sep 13:56 cenagoso.jpeg
-rw-r--r--@    1 jeff  staff   3.0K 18 Sep 13:56 patena.jpeg
-rw-r--r--@    1 jeff  staff    15K 20 Sep 22:01 carrocería.jpeg
-rw-r--r--@    1 jeff  staff   5.4K 20 Sep 22:01 escupitajo.jpeg
-rw-r--r--@    1 jeff  staff    12K 20 Sep 22:01 broche.jpeg
drwxr-xr-x@ 1895 jeff  staff    59K 26 Sep 17:17 .
-rw-r--r--@    1 jeff  staff    11K 26 Sep 17:17 encuadre.jpeg
```
