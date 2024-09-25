Please reproduce the issue and then upload **all of** your latest Server log file to an *external site*. If the log is too long or if its about a specific log line, upload that logline plus 100 lines before that and after that.

The logfiles are found in the same place as ffmpeg logs, right in the dashboard.
If you dont have access to the dashboard you can find your logfiles in the following locations:
- For Linux: `/var/lib/jellyfin/logs`
- For Windows: `%programdata%/jellyfin/logs`
- For Docker: You need to [mount](https://docs.docker.com/engine/storage/bind-mounts/) your config directory and then navigate to that mounts folder /logs

We recommend an external site like
- https://pastebin.com
- https://paste.debian.net/

Paste the contents of your logfile into the input of those webseits and click `Send`/`Create new Paste`, then copy the browsers URL and send it here in chat.
