Symlinks do not allow you to bypass permission issues. If you use symlinks in your Jellyfin library then Jellyfin must have permissions to read the destination of the symlink as if it were directly accessing it.

If this is a direct install the Jellyfin service user needs at least r-x permission on every step of the directory and r-- on the media files.

If this is a docker install the user the container is running as, assuming this is a rootless docker container, needs the same permissions as stated above.
