# Command line jobs

While Lute is almost solely a web app, it has some jobs that are run from the terminal, outside of the browser.

* `hello`: Say hi!  Proof-of-concept
* `language_export`: Get all terms from active books in the language, and write a data file of term frequencies and children.

## How to run the jobs

**These jobs are (currently) only runnable through the command line for pip installs.**

Open a terminal, change directory to your Lute folder, and enter the following commands:

```
source .venv/bin/activate    # Activate your virtual environment.
flask --app lute.app_factory cli <command_name> [arg1] [arg2...]
```

The `--app lute.app_factory` part is **required**[^these-calls-are-ugly].

Lute does not need to be running when you're running a command.

List all jobs:

```
flask --app lute.app_factory cli --help
```

To see help about a job:

```
flask --app lute.app_factory cli <command_name> --help
```

### Sample calls

```
flask --app lute.app_factory cli hello
flask --app lute.app_factory cli language_export Spanish sp_terms.cs
```

You can do things like [export environment variables](https://flask.palletsprojects.com/en/2.3.x/cli/#environment-variables-from-dotenv) to simplify your calls if you wish.

## config.yml file

If you have a [custom config.yml](./starting-and-stopping.md#custom-configyml), Lute jobs will use those settings; otherwise, it uses the built-in defaults.

## Why aren't these built into the UI?

Good question, here are some reasons:

* **Unsure how to add to UI.** Lute is primarily for reading, and I've tried to keep the UI clean and focused on that.  Some things are _related_ to Lute but don't necessarily fall within its main purpose.
* **Long-running jobs.** Some jobs might take a _long_ time to complete.  While there are ways to have the server communicate back to a browser client (WebSockets), I have no experience with these things.
* **"Good enough" is better than perfect.** Shipping something working is better than trying to perfect it.  Sometimes jobs are a hacky but effective way to get things out the door.

## Docker users

I'm sure there is a way to run the commands even if you're using Docker, but you may have to jump through some hoops.  It's janky, I know, but if you're technical perhaps you can do some jumping and let me know how you did it.  Otherwise, I can't guarantee that jobs will be used by _anybody_, other than a select few, so I'll leave it as it is for now!

---

[^these-calls-are-ugly]: _Note from the dev (me!):_ I recognize how ugly the "--app lute.app_factory" portion of the command is, but it is not trivial to get rid of.  The commands are built on part of the framework that Lute uses, and there is no easy way to avoid the "--app" flag, as far as I know.  I tried other design options, but they all had drawbacks.  In future, these jobs may be incorporated into Lute's UI.  For now, this is good enough.
