# On Mac OSX

`$ brew install postgres`

Now you should have a user with the same name of current loggined user. Eg. My login user is riyang, now the default user should be riyang.

The next step is you should change the `pg_hba.conf` to control the authentication way. Default is trust on my Mac OSX. 
So I need to create a new user(role) first, and then enable password authentication.
```
$ psql -U riyang
postgres=# CREATE USER postgres WITH PASSWORD 'postgres';
postgres=# \q
```

Then open the `pg_hba.conf`, change trust to password and restart postgres:
```
$ brew services restart postgresql
```

# On Debian/Linux

`$ apt-get install postgresql`

Now you should a system user with the name of `postgres`.

```
$ su - postgres psql
$ postgres=# CREATE USER postgres WITH PASSWORD 'postgres';
postgres=# \q
```

Likewise, modify the `pg_hba.conf` and restart service.
`$ services restart postgresql`
