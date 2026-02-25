Jellyfin Media Player v1 has been renamed to Jellyfin Desktop in v2.

An underlying library used by Jellyfin Desktop has a [large memory leak](https://github.com/jellyfin/jellyfin-desktop/issues/1091). This is causing further official packaging and releases to be put on hold. Concurrently, a rebuild of Jellyfin Desktop is being looked at using a different underlying framework (CEF instead of QT). Devs are working on getting a proper client that works for all the standard systems.
