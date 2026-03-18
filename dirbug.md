There's a bug in the current version of Jellyfin where if you rename or remove a bunch of directories on the filesystem, library updates can break, leaving "ghost" old entries for the changed/removed media and possibly preventing addition of new media to the library. In the server logs, you see errors like this:

```
jellyfin  | [12:24:32] [INF] [20] Emby.Server.Implementations.Library.LibraryManager: Removing item, Type: Folder, Name: Some-Video-File, Path: /some/local/path/that/does/not/exist/anymore, Id: 6f59b9a7-740c-6e76-9d76-a46058631272
jellyfin  | [12:24:32] [ERR] [20] Microsoft.EntityFrameworkCore.Database.Command: Failed executing DbCommand (1ms) [Parameters=[@__date_1='?' (DbType = DateTime), @__p_0='?' (Size = 664)], CommandType='Text', CommandTimeout='30']
jellyfin  | UPDATE "UserData" AS "u"
jellyfin  | SET "ItemId" = '00000000-0000-0000-0000-000000000001',
jellyfin  |     "RetentionDate" = @__date_1
jellyfin  | WHERE "u"."ItemId" IN (
jellyfin  |     SELECT "p"."value"
jellyfin  |     FROM json_each(@__p_0) AS "p"
jellyfin  | )
```

To resolve this, re-create the old/missing directories and kick off a rescan. You don't have to put files in them, just put the directories in place. Once the rescan is successful (check the logs for further errors), you can remove the empty directories.

[official issue is here](https://github.com/jellyfin/jellyfin/issues/15343)
