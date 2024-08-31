Make sure that your firewall is allowing Jellyfin through the firewall.

TCP port 8096 is mandatory.
TCP port 8920 is optional if you choose to have Jellyfin run HTTPS without a reverse proxy. (not recommended)
UDP port 1900 is for DLNA. (optional, LAN only, do not port forward on your router)
UDP port 7359 is for service discovery. (optional, but nice to have, LAN only, do not port forward on your router)

A lot of Linux distros either come with UFW (Uncomplicated Firewall) or it is available in their package manager. UFW is a simpler frontend for netfilter, replaces IPTables. Though UFW still adds rules via IPTables.

```sudo ufw allow 8096/tcp```
```sudo ufw allow 1900/udp```
```sudo ufw allow 7359/udp```

Make sure UFW is enabled. ```sudo ufw enable```. When UFW is disabled, any rules you create are not active.

In Windows if you ran the installer as an admin it should have prompted you at the end of the installation process to add jellyfin.exe to the Windows Firewall. If that prompt did not come up for whatever reason, go to the Windows Control Panel, Windows Firewall, and either add a rule to allow jellyfin.exe or add the ports listed above.

You can check the current status in the Windows Resource Monitor. Click Start > type "resource monitor" > click on the Network tab > expand the Listening Ports table. Find jellyfin.exe. There will be multiple of them on various ports. The Firewall Status column for port 8096 should be "Allowed, not restricted". If it is not that status, jellyfin.exe is not properly in your Windows Firewall.
