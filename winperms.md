Some external process (possibly Windows Update) seems to sometimes reset permissions on some Jellyfin directories, causing the server to not start after a reboot.

To fix this, run one of the following as Administrator:

Command (CMD):

```
icacls "C:\ProgramData\Jellyfin\Server" /grant "%USERNAME%:(F)" /T /inheritancelevel:d
```

PowerShell:

```
icacls "C:\ProgramData\Jellyfin\Server" /grant "%LOGNAME%:(F)" /T /inheritancelevel:d
```

Then try starting Jellyfin again (or reboot the server).