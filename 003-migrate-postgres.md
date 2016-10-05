
https://wiki.gentoo.org/wiki/PostgreSQL/QuickStart#Migrating_PostgreSQL

= Preparing to initialize the cluster

	kenneth@kennethd ~ $ cat /etc/conf.d/postgresql-9.5 | grep -vE '^#' | grep -v '^$'
	PGPORT="5432"
	START_TIMEOUT=10
	NICE_TIMEOUT=60
	RUDE_QUIT="YES"
	RUDE_TIMEOUT=30
	FORCE_QUIT="NO"
	FORCE_TIMEOUT=2
	PGDATA="/etc/postgresql-9.5/"
	DATA_DIR="/var/lib/postgresql/9.5/data"
	PG_INITDB_OPTS="--encoding=UTF8"


== 9.4 config ==

	kenneth@kennethd ~ $ sudo cat /etc/postgresql-9.4/postgresql.conf | grep -vE '^\s*#' | grep -v '^$'
	max_connections = 100                   # (change requires restart)
	shared_buffers = 128MB                  # min 128kB
	dynamic_shared_memory_type = posix      # the default is the first option
	log_timezone = 'UTC'
	datestyle = 'iso, mdy'
	timezone = 'UTC'
	lc_messages = 'C'                       # locale for system error message
	lc_monetary = 'en_US.UTF-8'                     # locale for monetary formatting
	lc_numeric = 'en_US.UTF-8'                      # locale for number formatting
	lc_time = 'en_US.UTF-8'                         # locale for time formatting
	default_text_search_config = 'pg_catalog.english'
	plperl.on_init = 'use utf8; use re; package utf8; require "utf8_heavy.pl";'


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

== 9.5 config ==


