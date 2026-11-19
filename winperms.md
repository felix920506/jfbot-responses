Some external process (possibly Windows Update) seems to sometimes reset permissions on some Jellyfin directories, causing the server to not start after a reboot.

To fix this if you're running the tray app, run one of the following as Administrator:

Command (CMD):

```
icacls "%ProgramData%\\Jellyfin\Server" /grant "%USERNAME%:(OI)(CI)(F)" /T
```

PowerShell:

```
icacls "$env:ProgramData\Jellyfin\Server" /grant "$($env:USERNAME):(OI)(CI)(F)" /T
```

Then try starting Jellyfin again (or reboot the server).

If you're running as a service you have to use the user the service runs instead of %USERNAME%/($env:USERNAME).