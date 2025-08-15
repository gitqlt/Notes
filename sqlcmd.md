sqlcmd: Official Microsoft SQL Server command line tool
====

#### List database names
    $ docker run --rm -it mcr.microsoft.com/mssql-tools
    /opt/mssql-tools/bin/sqlcmd -S $DB_HOST -U $DB_USER -P "$DB_PASSW" -Q 'SELECT name FROM master.sys.databases'

#### DB size
    $ docker run --rm -it mcr.microsoft.com/mssql-tools
    /opt/mssql-tools/bin/sqlcmd -S $DB_HOST -U $DB_USER -P "$DB_PASSW" -d <database>
    1> EXEC sp_spaceused;
    2> GO

