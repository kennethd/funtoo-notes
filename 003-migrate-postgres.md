
https://wiki.gentoo.org/wiki/PostgreSQL/QuickStart#Migrating_PostgreSQL

== 9.4 config ==

kenneth@kennethd ~ $ sudo cat  /etc/postgresql-9.4/pg_hba.conf 
# TYPE  DATABASE        USER            ADDRESS                 METHOD

# "local" is for Unix domain socket connections only
local   all             all                                     trust
# IPv4 local connections:
host    all             all             127.0.0.1/32            trust
# IPv6 local connections:
host    all             all             ::1/128                 trust
# Allow replication connections from localhost, by a user with the
# replication privilege.
#local   replication     postgres                                trust
#host    replication     postgres        127.0.0.1/32            trust
#host    replication     postgres        ::1/128                 trust

