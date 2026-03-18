Jellyfin Media Player v1 has been renamed to Jellyfin Desktop in v2.

An underlying library used by Jellyfin Desktop has a [large memory leak](https://github.com/jellyfin/jellyfin-desktop/issues/1091). This was discovered after the new version started being released and prompted a rewrite to use a different backend library, which is now available for testing. See the [Jellyfin Desktop CEF](https://github.com/jellyfin-labs/jellyfin-desktop-cef) repository to test the new version!
