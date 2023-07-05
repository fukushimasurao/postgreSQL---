# DBお勉強用

- `$ docker-compose up -d`
- `$ docker exec -it postgres /bin/bash`

*コンテナ内にて*

- `# su postgres -c "pg_ctl --help"`

- postgre サーバーストップ
- `root@87999a1fa23e:/# su postgres -c 'pg_ctl -D /var/lib/postgresql/data stop'`

- postgre サーバー起動
- `root@87999a1fa23e:/# su postgres -c 'pg_ctl -D /var/lib/postgresql/data start'`

- postgre サーバー確認

```bash
root@87999a1fa23e:/# su postgres -c 'pg_ctl -D /var/lib/postgresql/data status'
pg_ctl: server is running (PID: 1)
/usr/lib/postgresql/14/bin/postgres
```

- ユーザー作成

```bash
$ docker-compose exec db bash
root@87999a1fa23e:/# su - postgres
postgres@87999a1fa23e:~$ createuser hogehoge
postgres@87999a1fa23e:~$ psql
psql (14.8 (Debian 14.8-1.pgdg120+1))
Type "help" for help.

postgres=# \du 
                                   List of roles
 Role name |                         Attributes                         | Member of 
-----------+------------------------------------------------------------+-----------
 hogehoge  |                                                            | {}
 postgres  | Superuser, Create role, Create DB, Replication, Bypass RLS | {}
```

- ユーザー削除

```bash
postgres@87999a1fa23e:~$ dropuser hogehoge
postgres@87999a1fa23e:~$ psql
psql (14.8 (Debian 14.8-1.pgdg120+1))
Type "help" for help.

postgres=# \du
                                   List of roles
 Role name |                         Attributes                         | Member of 
-----------+------------------------------------------------------------+-----------
 postgres  | Superuser, Create role, Create DB, Replication, Bypass RLS | {}
```
