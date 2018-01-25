# DB2 Command

## Table

```SELECT COLNAME FROM SYSCAT.COLUMNS WHERE TABNAME='PRELVL' ```

```
select * from sysibm.systables
where owner/CREATOR = 'SCHEMA'
and name like '%CUR%'AND
and type = 'T';
```

```db2move server_db_name export -sn schema_name ```

```db2move server_db_name export -tn table_name ```

 Export DDL:
 ```db2look -d deltadb -z delta -e -o ~/delta/db_name.ddl
 -- need update the db name in ddl
 ```

Restore DB Image：
```
list applications

force application ([app id])

drop database [ db_name ]

restore database [db_name ] from [ file_path ] taken at [ timestamp ]

restore database [db_name ] from [ file_path ] taken at [ timestamp ]  redirect generate script  [  ./tmp.sql ]

db2 -xvf   tmp.sql

NOTES:  File_Path not file name. Check file mode set 777 mode

db2 backup

db2 backup db [db_name] to [file_path] 

db2 export data

| db2 "export to bkupevtlog90.del of del select * from bkup.evtlog1 where loaddt>current date-90 days" |      |
| ---------------------------------------- | ---- |
| db2 "export to bkupevtlog30.del of del select * from bkup.evtlog1 where loaddt>current date-30 days" |      |

```
## Instance

```
db2 -tvsf filename.sql    -- run sql script file
```

