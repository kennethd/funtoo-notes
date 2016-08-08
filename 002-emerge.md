kenneth@kennethd ~ $ sudo emerge -1v dev-lang/python:2.7 dev-lang/python:3.3


	 * You need to add a user running a service using Courier's
	 * authdaemon to the 'mail' group. For example, do:
	 *      gpasswd -a postfix mail
	 * to add the 'postfix' user to the 'mail' group.
	 * pwcheck and saslauthd home directories have moved to:
	 *   /run/saslauthd, using tmpfiles.d
	>>> dev-libs/cyrus-sasl-2.1.26-r10 merged.
	>>> Regenerating /etc/ld.so.cache...

	 * Messages for package dev-lang/python-3.4.5:

	 * You have just upgraded from an older version of Python.
	 * 
	 * Please adjust PYTHON_TARGETS (if so desired), and run emerge with the --newuse or --changed-use option to rebuild packages installing python modules.

	 * Messages for package app-eselect/eselect-python-20151117-r2:

	 * This package will overwrite one or more files that may belong to other
	 * packages (see list below). You can use a command such as `portageq
	 * owners / <filename>` to identify the installed package that owns a
	 * file. If portageq reports that only one package owns a file then do
	 * NOT file a bug report. A bug report is only useful if it identifies at
	 * least two or more packages that are known to install the same file(s).
	 * If a collision occurs and you can not explain where the file came from
	 * then you should simply ignore the collision since there is not enough
	 * information to determine if a real problem exists. Please do NOT file
	 * a bug report at http://bugs.gentoo.org unless you report exactly which
	 * two packages install the same file(s). See
	 * http://wiki.gentoo.org/wiki/Knowledge_Base:Blockers for tips on how to
	 * solve the problem. And once again, please do NOT file a bug report
	 * unless you have completely understood the above message.
	 * 
	 * Detected file collision(s):
	 * 
	 *      /usr/bin/python2
	 *      /usr/bin/python
	 *      /usr/bin/python3
	 *      /usr/bin/python-config
	 *      /usr/bin/pydoc
	 *      /usr/bin/2to3
	 * 
	 * 
	 * Package 'app-eselect/eselect-python-20151117-r2' merged despite file
	 * collisions. If necessary, refer to your elog messages for the whole
	 * content of the above message.

	 * Messages for package dev-db/postgresql-9.5.3:

	 * Unable to find kernel sources at /usr/src/linux
	 * Unable to calculate Linux Kernel version for build, attempting to use running version
	 * Unable to check for the following kernel config options due
	 * to absence of any configured kernel sources or compiled
	 * config:
	 *  - SYSVIPC
	 * You're on your own to make sure they are set if needed.
	 * If you need a global psqlrc-file, you can place it in:
	 *     /etc/postgresql-9.5/
	 * 
	 * It looks like this is your first time installing PostgreSQL. Run the
	 * following command in all active shells to pick up changes to the default
	 * environment:
	 *     source /etc/profile
	 * 
	 * Gentoo specific documentation:
	 * https://wiki.gentoo.org/wiki/PostgreSQL
	 * 
	 * Official documentation:
	 * http://www.postgresql.org/docs/9.5/static/index.html
	 * 
	 * The default location of the Unix-domain socket is:
	 *     /run/postgresql/
	 * 
	 * Before initializing the database, you may want to edit PG_INITDB_OPTS
	 * so that it contains your preferred locale in:
	 *     /etc/conf.d/postgresql-9.5
	 * 
	 * Then, execute the following command to setup the initial database
	 * environment:
	 *     emerge --config =dev-db/postgresql-9.5.3

	 * Messages for package net-libs/courier-authlib-0.66.4:

	 * The dev-tcltk/expect package is not installed.
	 * Without it, you will not be able to change system login passwords.
	 * However non-system authentication modules (LDAP, MySQL, PostgreSQL,
	 * and others) will work just fine.
	 * Both gdbm and berkdb selected. Using gdbm.

	 * Messages for package dev-libs/cyrus-sasl-2.1.26-r10:

	 * You need to add a user running a service using Courier's
	 * authdaemon to the 'mail' group. For example, do:
	 *      gpasswd -a postfix mail
	 * to add the 'postfix' user to the 'mail' group.
	 * pwcheck and saslauthd home directories have moved to:
	 *   /run/saslauthd, using tmpfiles.d
	>>> Auto-cleaning packages...

	>>> No outdated packages were found on your system.

	 * GNU info directory index is up-to-date.

	!!! existing preserved libs:
	>>> package: dev-lang/python-3.3.5-r8
	 *  - /usr/lib64/libpython3.3.so.1.0
	 *      used by /usr/lib64/libboost_python-3.3.so.1.57.0 (dev-libs/boost-1.57.0)
	 *      used by /usr/lib64/python3.3/site-packages/Crypto/Cipher/_AES.cpython-33.so (dev-python/pycrypto-2.6.1-r1)
	 *      used by /usr/lib64/python3.3/site-packages/Crypto/Cipher/_ARC2.cpython-33.so (dev-python/pycrypto-2.6.1-r1)
	 *      used by 41 other files
	Use emerge @preserved-rebuild to rebuild packages using these libraries


kenneth@kennethd ~ $ sudo emerge -auvO portage

	 * 
	 * The 'websync' module has now been properly renamed to 'webrsync'
	 * Please update your repos.conf/gentoo.conf file if needed.
	 * 
	 * This release of portage removed the new squashfs sync module 
	 * introduced in portage-2.2.19.
	 * Look for it to be released as an installable portage module soon.
	 * This will allow it to develop at it's own pace partially independant
	 * of portage
	 * 




kenneth@kennethd ~ $ sudo emerge -1pv =app-antivirus/clamav-0.99.2 
!!! Found 2 make.conf files, using both '/etc/make.conf' and '/etc/portage/make.conf'

These are the packages that would be merged, in order:

Calculating dependencies... done!
[ebuild     U  ] app-antivirus/clamav-0.99.2::gentoo [0.98.7-r1::gentoo] USE="bzip2 clamdtop iconv ipv6 -libressl -metadata-analysis-api -milter (-selinux) -static-libs (-uclibc)" 15,691 KiB
[blocks B      ] <app-antivirus/clamav-0.99 ("<app-antivirus/clamav-0.99" is hard blocking app-antivirus/clamav-0.99.2)

Total: 1 package (1 upgrade), Size of downloads: 15,691 KiB
Conflict: 1 block (1 unsatisfied)

 * Error: The above package list contains packages which cannot be
 * installed at the same time on the same system.

  (app-antivirus/clamav-0.99.2:0/0::gentoo, ebuild scheduled for merge) pulled in by
    =app-antivirus/clamav-0.99.2
    app-antivirus/clamav required by @selected


For more information about Blocked Packages, please refer to the following
section of the Gentoo Linux x86 Handbook (architecture is irrelevant):

https://wiki.gentoo.org/wiki/Handbook:X86/Working/Portage#Blocked_packages



kenneth@kennethd ~ $ emerge -avC app-antivirus/clamav 
!!! Found 2 make.conf files, using both '/etc/make.conf' and '/etc/portage/make.conf'
This action requires superuser access...
Would you like to add --pretend to options? [Yes/No] Yes
 * This action can remove important packages! In order to be safer, use
 * `emerge -pv --depclean <atom>` to check for reverse dependencies before
 * removing packages.

>>> These are the packages that would be unmerged:

 app-antivirus/clamav
    selected: 0.98.7-r1 
   protected: none 
     omitted: none 

All selected packages: =app-antivirus/clamav-0.98.7-r1

>>> 'Selected' packages are slated for removal.
>>> 'Protected' and 'omitted' packages will not be removed.

kenneth@kennethd ~ $ sudo emerge -avC app-antivirus/clamav 
kenneth@kennethd ~ $ sudo emerge -av app-antivirus/clamav 

	 * You must run freshclam manually to populate the virus database files
	 * before starting clamav for the first time.
	 * 
	>>> app-antivirus/clamav-0.99.2 merged.
	>>> Regenerating /etc/ld.so.cache...

	>>> Recording app-antivirus/clamav in "world" favorites file...

	 * Messages for package app-antivirus/clamav-0.99.2:

	 * You must run freshclam manually to populate the virus database files
	 * before starting clamav for the first time.
	 * 
	>>> Auto-cleaning packages...

	>>> No outdated packages were found on your system.

	 * GNU info directory index is up-to-date.

	!!! existing preserved libs:
	>>> package: dev-lang/python-3.3.5-r8
	 *  - /usr/lib64/libpython3.3.so.1.0
	 *      used by /usr/lib64/libboost_python-3.3.so.1.57.0 (dev-libs/boost-1.57.0)
	 *      used by /usr/lib64/python3.3/site-packages/Crypto/Cipher/_AES.cpython-33.so (dev-python/pycrypto-2.6.1-r1)
	 *      used by /usr/lib64/python3.3/site-packages/Crypto/Cipher/_ARC2.cpython-33.so (dev-python/pycrypto-2.6.1-r1)
	 *      used by 41 other files
	Use emerge @preserved-rebuild to rebuild packages using these libraries

kenneth@kennethd ~ $ sudo freshclam 
	Password: 
	ClamAV update process started at Mon Aug  8 18:16:15 2016
	Downloading main.cvd [100%]
	main.cvd updated (version: 57, sigs: 4218790, f-level: 60, builder: amishhammer)
	Downloading daily.cvd [100%]
	daily.cvd updated (version: 22051, sigs: 492255, f-level: 63, builder: neo)
	Downloading bytecode.cvd [100%]
	bytecode.cvd updated (version: 283, sigs: 53, f-level: 63, builder: neo)
	Database updated (4711098 signatures) from database.clamav.net (IP: 64.6.100.177)
	WARNING: Clamd was NOT notified: Can't connect to clamd through /var/run/clamav/clamd.sock: No such file or directory



kenneth@kennethd ~ $ sudo emerge --pretend --update --newuse --deep --with-bdeps=y @world







