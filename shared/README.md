# Shared data dir

This directory will be mounted into both the pgadmin and postgres containers under the path `/shared`.
This can be used to export or import data to or from the database using pgadmin.

## Export table data

### As SQL insert statements

This is useful when importing into PGAdmin where you don't have access to the filesystem. Instead of the export
option, we're going to use the Backup option

[Info on this dialog here](https://www.pgadmin.org/docs/pgadmin4/development/backup_dialog.html)

1. In PGAdmin, right-click the table you want to export from, and select *Backup...*
2. Ensure the Filename is set to `/shared/FILENAME.sql`, replacing `FILENAME` with whatever you want
3. In the Data Options tab, ensure `Only data` is enabled
4. In the Query Options tab, ensure `Use INSERT Commands` is enabled
5. In the Table Options tab, ensure `Use Column INSERTS` is enabled
6. Backup

You can now copy and paste this into another instance of PGAdmin, in the Query tool
