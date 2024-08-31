Before playback, Jellyfin clients run a bandwidth test to determine the available bandwidth between the devices and calculates an appropriate streaming bitrate. If the calculated bitrate is lower than that of the source media, Jellyfin will transcode the media to a lower bandwidth on the server. There is no way to disable this without disabling transcoding for the user altogether.

Below are a few reasons that may cause Jellyfin to transcode even if there *seems* to be sufficient bandwidth:
- The device is on Wifi or the data passes through a wireless bridge.
- Faulty and / or underpowered Networking Equipment.
- Low end client devices.
- ISP QoS, routing and / or peering. This one cannot be fixed without switching ISPs.