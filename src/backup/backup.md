# Backup

Lute provides a simple backup facility that creates copies your Sqlite database and all of your term images to a backup folder that you specify.  You don't _have_ to use it, but please be sure that you have some kind of backup strategy in place!

> Back up your stuff!

## Configuration

Backup is configured in the Settings.

| Setting | Values | Notes |
| --- | --- | --- |
| Backup enabled | yes or no | Set to "yes" if you want to run them through the Lute UI or have Lute do daily backups, and "no" if you're handling your own backups with scripts or whatever. |
| Backup directory **(Non-Docker users only)** | Full directory path | This is the *existing* directory where a gzipped database export, and copy of all of your images, will be sent.  Set this to something that is backed up, such as to a DropBox folder or similar.  This is disabled for Docker users, because the backup directory has to be mounted to a host folder. |
| Run backups automatically (daily) | yes or no | If `yes`, Lute will run the backup *from the Home page* every day.  Note that this is only from the Home page, so if you have a book open for reading for 2 weeks, it won't be backed up. :-) |
| Warn if backup hasn't run in a week | yes or no | If `yes`, Lute will print a warning *on the Home page* if the last backup was run more than one week ago.  Again, this is only from the home page. |
| Retain backup count | Number | The number of automatic backup files to keep.  Backups are created with date-time stamp added (e.g. `lute_backup_2023-04-19_204452.db.gz`), and Lute only keeps the specified count of most recent backups.  Note that this number is only used for automatic backups.  For "manual" backups (where you click the link to create a backup from the Home page), you have to delete old files. |

## Manual and automatic backups

There are two kinds of backups, "manual" and "automatic".  Both are placed in the folder you specify in your settings.

* Manual backups are created when you click "create backup" from the Home page.  All of these are kept.
* Automatic backups are created every day by Lute, if you enable them, **but only from the home screen** (see below).  Lute only stores a limited number of automatic backups.

Here's an example on my system:

```
$ ls -1 zz_backup/
lute_backup_2023-04-20_204452.db.gz
lute_backup_2023-04-21_204512.db.gz
lute_backup_2023-04-22_204519.db.gz
lute_backup_2023-04-23_204547.db.gz
lute_backup_2023-04-24_204604.db.gz
manual_lute_backup_2023-04-19_204132.db.gz
manual_lute_backup_2023-04-19_204204.db.gz
manual_lute_backup_2023-04-19_204652.db.gz
userimages_backup/
```

* I only have 5 "automatic" backups
* I have as many `manual_` backups as I need/want
* There is only one `userimages_backup/` folder, ever.

## Automatic backups only run from the Home screen

If you just leave Lute running all the time, and have it opened to a book that you're reading, Lute's automatic backup process **doesn't start**.

Lute only runs the daily automated backups from the Home screen -- so, periodically, head on to Lute Home, and wait for that to complete.