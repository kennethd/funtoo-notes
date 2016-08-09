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



kenneth@kennethd ~ $ sudo emerge --update --newuse --deep --with-bdeps=y @world

(226 packages updated)

kenneth@kennethd ~ $ sudo emerge -av --depclean

	>>> These are the packages that would be unmerged:

Note, the following list is followed by the message:

	>>> 'Selected' packages are slated for removal.
	>>> 'Protected' and 'omitted' packages will not be removed.

I have no protected packages, but some are omitted -- perhaps due to specific version dependencies:

	 dev-python/characteristic
		selected: 14.3.0-r1 
	   protected: none 
		 omitted: none 

looks harmless to remove

	 virtual/perl-Attribute-Handlers
		selected: 0.970.0 
	   protected: none 
		 omitted: none 

looks harmless to remove

	 app-arch/rpm2targz
		selected: 9.0.0.5g 
	   protected: none 
		 omitted: none 

looks harmless to remove

	 app-admin/python-updater
		selected: 0.13 
	   protected: none 
		 omitted: none 

deprecated, see http://www.funtoo.org/News:Python_Updater_Deprecation

"As some users have noticed, the python-updater package, a tool for scanning and rebuilding python packages after major Python version updates is now removed. As of Nov 28, python-updater is no longer required. After merging new version of python ebuilds, the following steps are required:

	Portage rebuild
	# emerge --oneshot sys-apps/portage

This ensures that unconditional dependencies are properly installed."


That page also refers to http://www.funtoo.org/News:Unfork_Tree_is_Live!

note point 3: "Try updating @system first, before attempting @world."; Oops.


	 dev-db/tinycdb
		selected: 0.77-r2 
	   protected: none 
		 omitted: none 

Can always reinstall if needed

	 mail-client/roundcube
		selected: 1.0.6 
	   protected: none 
		 omitted: 1.2.0 

This looks like I have "pinned" roundcube to 1.0.6, but 1.2.0 is available

	 dev-python/packaging
		selected: 15.3-r2 
	   protected: none 
		 omitted: none 

Probably part of the Python kerfluffle above

	 dev-php/PEAR-Crypt_GPG
		selected: 1.3.2 
	   protected: none 
		 omitted: none 

Doesn't seem system-debilitating, I haven't paid attention much to PHP library
deprecations, might have been required by previous version of roundcube?

	 virtual/httpd-php
		selected: 5.5 
	   protected: none 
		 omitted: 7.0 

PHP pinned to 5.5?  It seems so:
kenneth@kennethd ~ $ php --version 
PHP 5.5.30-pl0-gentoo (cli) (built: Nov 11 2015 21:39:58) 

	 dev-php/PEAR-Net_Sieve
		selected: 1.3.3 
	   protected: none 
		 omitted: none 

Doesn't seem system-debilitating, I haven't paid attention much to PHP library
deprecations, might have been required by previous version of roundcube?

	 dev-lang/python
		selected: 3.3.5-r8 
	   protected: none 
		 omitted: 2.7.12 3.4.5 

The Python news page above mentions the version of python used by system tools
is now 3.3, it looks like my default python is 2.7:

kenneth@kennethd ~ $ python --version 
Python 2.7.12

	 dev-lang/php
		selected: 5.5.30 
	   protected: none 
		 omitted: 7.0.9-r2 

PHP pinned to 5.5?  It seems so:
kenneth@kennethd ~ $ php --version 
PHP 5.5.30-pl0-gentoo (cli) (built: Nov 11 2015 21:39:58) 

	 sys-libs/db
		selected: 4.8.30-r2 
	   protected: none 
		 omitted: 5.3.28-r3 6.0.30-r2 

Not sure what this package is, I expect it is the specific version something else depends on

	 dev-db/postgresql
		selected: 9.4.5-r1 
	   protected: none 
		 omitted: 9.5.3 

Postgres is pinned to specific version too:

	kenneth@kennethd ~ $ psql --version 
	psql (PostgreSQL) 9.4.5

It was originally installed with:

	kennethd ~ # emerge --config dev-db/postgresql:9.4

Though this doesn't explain to me why none of the following have been installed
(all of which are listed by `equery g postgresql:9.4`):

	dev-db/postgresql-9.4.5-r2
	dev-db/postgresql-9.4.6
	dev-db/postgresql-9.4.7
	dev-db/postgresql-9.4.8

Current USE may be interesting:

kenneth@kennethd ~ $  emerge --info | grep ^USE
!!! Found 2 make.conf files, using both '/etc/make.conf' and '/etc/portage/make.conf'
USE="acl amd64 apache2 authdaemond berkdb bzip2 clamdtop cracklib crypt cxx gdbm iconv icu imap ipv6 maildir mmx modules mudflap multilib mysql ncurses nls nptl openmp pam pcre postgres python readline resolvconf sasl smtp spamassassin spell sse sse2 ssl tcpd unicode urandom vhosts xattr xml zlib" ABI_X86="64" APACHE2_MODULES="actions alias auth_basic authn_alias authn_anon authn_dbm authn_default authn_file authz_dbm authz_default authz_groupfile authz_host authz_owner authz_user autoindex cache cgi cgid dav dav_fs dav_lock deflate dir disk_cache env expires ext_filter file_cache filter headers include info log_config logio mem_cache mime mime_magic negotiation rewrite setenvif speling status unique_id userdir usertrack vhost_alias authn_core authz_core socache_shmcb unixd" CALLIGRA_FEATURES="kexi words flow plan sheets stage tables krita karbon braindump author" CAMERAS="ptp2" COLLECTD_PLUGINS="df interface irq load memory rrdtool swap syslog" CPU_FLAGS_X86="aes mmx mmxext popcnt sse sse2 sse3 sse4_1 sse4_2 ssse3" ELIBC="glibc" GPSD_PROTOCOLS="ashtech aivdm earthmate evermore fv18 garmin garmintxt gpsclock itrax mtk3301 nmea ntrip navcom oceanserver oldstyle oncore rtcm104v2 rtcm104v3 sirf superstar2 timing tsip tripmate tnt ublox ubx" GRUB_PLATFORMS="efi-64 pc" INPUT_DEVICES="evdev synaptics keyboard mouse" KERNEL="linux" LCD_DEVICES="bayrad cfontz cfontz633 glk hd44780 lb216 lcdm001 mtxorb ncurses text" LIBREOFFICE_EXTENSIONS="presenter-console presenter-minimizer" OFFICE_IMPLEMENTATION="libreoffice" PHP_TARGETS="php5-6 php5-5" PYTHON_SINGLE_TARGET="python3_4" PYTHON_TARGETS="python2_7 python3_4" QEMU_SOFTMMU_TARGETS="i386 x86_64" QEMU_USER_TARGETS="i386 x86_64" RUBY_TARGETS="ruby20 ruby21 ruby22" USERLAND="GNU" XTABLES_ADDONS="quota2 psd pknock lscan length2 ipv4options ipset ipp2p iface geoip fuzzy condition tee tarpit sysrq steal rawnat logmark ipmark dhcpmac delude chaos account"


Before continuing with that, I want to run the recommended @system update from the wiki.

Oh my, more conflicts...

kenneth@kennethd ~ $ sudo emerge -auDN @system 

	WARNING: One or more updates/rebuilds have been skipped due to a dependency conflict:

	net-libs/courier-unicode:0

	  (net-libs/courier-unicode-1.4:0/0::gentoo, ebuild scheduled for merge) conflicts with
		=net-libs/courier-unicode-1.3 required by (net-libs/courier-authlib-0.66.4:0/0::gentoo, installed)
		^                         ^^^

Indeed, it depends on the earlier version explicitly:

	 * dependency graph for net-libs/courier-authlib-0.66.4
	 `--  net-libs/courier-authlib-0.66.4  amd64 
	   `--  net-libs/courier-unicode-1.3  (=net-libs/courier-unicode-1.3) amd64 
	   `--  sys-libs/db-6.0.30-r2  (sys-libs/db) unknown 
	[ net-libs/courier-authlib-0.66.4 stats: packages (12), max depth (1) ]

while:

kenneth@kennethd ~ $ equery g net-mail/courier-imap

	 * dependency graph for net-mail/courier-imap-4.16.2-r1
	 `--  net-mail/courier-imap-4.16.2-r1  ~amd64 
	   `--  net-libs/courier-authlib-0.66.4  (>=net-libs/courier-authlib-0.61) amd64 
	   `--  net-libs/courier-unicode-1.4  (>=net-libs/courier-unicode-1.3) ~amd64 

though that ">=net-libs/courier-unicode-1.13" might suggest pinning it @ 1.13 might work for everyone

kenneth@kennethd ~ $ equery list -po net-libs/courier-unicode
	 * Searching for courier-unicode in net-libs ...
	[-P-] [  ] net-libs/courier-unicode-1.1:0
	[IP-] [  ] net-libs/courier-unicode-1.3:0
	[-P-] [  ] net-libs/courier-unicode-1.4:0

it seems a bad idea to pollute the world file, but as an experiment:

kenneth@kennethd ~ $ sudo emerge --noreplace --ask =net-libs/courier-unicode-1.3 

	These are the packages that would be merged, in order:

	 * net-libs/courier-unicode

	Would you like to add these packages to your world favorites? [Yes/No] Yes
	>>> Recording net-libs/courier-unicode in "world" favorites file...

kenneth@kennethd ~ $ sudo emerge -auDN @system 

	WARNING: One or more updates/rebuilds have been skipped due to a dependency conflict:

	net-libs/courier-unicode:0

	  (net-libs/courier-unicode-1.4:0/0::gentoo, ebuild scheduled for merge) conflicts with
		=net-libs/courier-unicode-1.3 required by (net-libs/courier-authlib-0.66.4:0/0::gentoo, installed)

No change.

Doesn't look like I successfully "pinned" the package to 1.3 in the world file either:

kenneth@kennethd ~ $ grep courier /var/lib/portage/world
	net-libs/courier-authlib
	net-libs/courier-unicode
	net-mail/courier-imap

Checking my earlier docs, I haven't gotten around to doing anything special to
configure Courier, so I amm temporarily removing it:

kenneth@kennethd ~ $ sudo emerge -avC net-libs/courier-authlib net-mail/courier-imap

trying again...

kenneth@kennethd ~ $  sudo emerge -auDN @system 

These are the packages that would be merged, in order:

Calculating dependencies... done!
[ebuild  N     ] net-libs/courier-authlib-0.66.4  USE="berkdb crypt gdbm mysql pam postgres -debug -ldap -libressl -sqlite -static-libs" 
[ebuild  N     ] net-mail/courier-imap-4.16.2-r1  USE="berkdb gdbm ipv6 -debug -fam -gnutls -libressl (-selinux) -trashquota" 


hmmm...

== MASKING VERSIONS >1.3

kenneth@kennethd ~ $ sudo mkdir  /etc/portage/package.mask 
kenneth@kennethd ~ $ sudo mkdir  /etc/portage/package.mask/net-libs 
kenneth@kennethd ~ $ sudo sh -c 'echo ">net-libs/courier-unicode-1.3" >/etc/portage/package.mask/net-libs/courier-unicode' 
kenneth@kennethd ~ $ cat /etc/portage/package.mask/net-libs/courier-unicode 
>net-libs/courier-unicode-1.3

kenneth@kennethd ~ $  sudo emerge -auDN @system 
!!! Found 2 make.conf files, using both '/etc/make.conf' and '/etc/portage/make.conf'

These are the packages that would be merged, in order:

Calculating dependencies... done!
[ebuild  N     ] net-libs/courier-unicode-1.3 
[ebuild  N     ] net-libs/courier-authlib-0.66.4  USE="berkdb crypt gdbm mysql pam postgres -debug -ldap -libressl -sqlite -static-libs" 
[ebuild  N     ] net-mail/courier-imap-4.16.2-r1  USE="berkdb gdbm ipv6 -debug -fam -gnutls -libressl (-selinux) -trashquota" 

Would you like to merge these packages? [Yes/No] 

...

 * Please read http://www.courier-mta.org/imap/INSTALL.html#upgrading
 * and remove TLS_DHPARAMS from configuration files or run mkdhparams
 * For a quick-start howto please refer to
 * courier-imap-gentoo.readme in /usr/share/doc/courier-imap-4.16.2-r1

 * Messages for package net-libs/courier-authlib-0.66.4:

 * The dev-tcltk/expect package is not installed.
 * Without it, you will not be able to change system login passwords.
 * However non-system authentication modules (LDAP, MySQL, PostgreSQL,
 * and others) will work just fine.
 * Both gdbm and berkdb selected. Using gdbm.

 * Messages for package net-mail/courier-imap-4.16.2-r1:

 * Please read http://www.courier-mta.org/imap/INSTALL.html#upgrading
 * and remove TLS_DHPARAMS from configuration files or run mkdhparams
 * For a quick-start howto please refer to
 * courier-imap-gentoo.readme in /usr/share/doc/courier-imap-4.16.2-r1



and...

kenneth@kennethd ~ $ sudo emerge -av dev-tcltk/expect




== Re-reviewing depclean output

>>> These are the packages that would be unmerged:

 dev-python/characteristic
    selected: 14.3.0-r1 
   protected: none 
     omitted: none 

 virtual/perl-Attribute-Handlers
    selected: 0.970.0 
   protected: none 
     omitted: none 

 mail-client/roundcube
    selected: 1.0.6 
   protected: none 
     omitted: 1.2.0 

 dev-python/packaging
    selected: 15.3-r2 
   protected: none 
     omitted: none 

 dev-db/tinycdb
    selected: 0.77-r2 
   protected: none 
     omitted: none 

 app-admin/python-updater
    selected: 0.13 
   protected: none 
     omitted: none 

 app-arch/rpm2targz
    selected: 9.0.0.5g 
   protected: none 
     omitted: none 

 virtual/httpd-php
    selected: 5.5 
   protected: none 
     omitted: 7.0 

 dev-php/PEAR-Crypt_GPG
    selected: 1.3.2 
   protected: none 
     omitted: none 

 dev-php/PEAR-Net_Sieve
    selected: 1.3.3 
   protected: none 
     omitted: none 

 dev-lang/python
    selected: 3.3.5-r8 
   protected: none 
     omitted: 2.7.12 3.4.5 

 dev-lang/php
    selected: 5.5.30 
   protected: none 
     omitted: 7.0.9-r2 

 sys-libs/db
    selected: 4.8.30-r2 
   protected: none 
     omitted: 5.3.28-r3 6.0.30-r2 

 dev-db/postgresql
    selected: 9.4.5-r1 
   protected: none 
     omitted: 9.5.3 




kenneth@kennethd ~ $ eselect python list
Available Python interpreters:
  [1]   python2.7 *
  [2]   python3.3
  [3]   python3.4
kenneth@kennethd ~ $ sudo eselect python set --python3 python3.4
kenneth@kennethd ~ $ eselect python list --python3
Available Python 3 interpreters:
  [1]   python3.3
  [2]   python3.4 *
kenneth@kennethd ~ $ sudo eselect python set  python3.4
kenneth@kennethd ~ $ eselect python list
Available Python interpreters:
  [1]   python2.7
  [2]   python3.3
  [3]   python3.4 *
kenneth@kennethd ~ $ python --version
Python 3.4.5


kenneth@kennethd ~ $ sudo eselect postgresql set 9.5
Setting 9.5 as the default installation...
        Removing old links...done.
        Generating new links...done.
Setting 9.5 as default was successful!


Finally allowing depclean to do its thing results in:


 * Messages for package dev-db/postgresql-9.4.5-r1:

 * Have you dumped and/or migrated the 9.4 database cluster?
 *      https://wiki.gentoo.org/wiki/PostgreSQL/QuickStart#Migrating_PostgreSQL

 * GNU info directory index is up-to-date.

 * IMPORTANT: 11 config files in '/etc' need updating.
 * See the CONFIGURATION FILES section of the emerge
 * man page to learn how to update config files.


kenneth@kennethd ~ $ sudo revdep-rebuild -v -- --ask 
!!! Found 2 make.conf files, using both '/etc/make.conf' and '/etc/portage/make.conf'
 * This is the new python coded version
 * Please report any bugs found using it.
 * The original revdep-rebuild script is installed as revdep-rebuild.sh
 * Please file bugs at: https://bugs.gentoo.org/
 * Collecting system binaries and libraries
 * Collecting dynamic linking informations
 * Scanning files
 * Checking dynamic linking consistency

Your system is consistent



kenneth@kennethd ~ $ sudo eix-test-obsolete 
Password: 

No non-matching entries in /etc/portage/package.keywords
No non-matching entries in /etc/portage/package.accept_keywords
No non-matching entries in /etc/portage/package.mask
No non-matching entries in /etc/portage/package.unmask
No non-matching or empty entries in /etc/portage/package.use
No non-matching or empty entries in /etc/portage/package.env
No non-matching or empty entries in /etc/portage/package.license
No non-matching or empty entries in /etc/portage/package.accept_restrict
No non-matching or empty entries in /etc/portage/package.cflags
The names of all installed packages are in the database.

No  redundant  entries in /etc/portage/package.{,accept_}keywords
No uninstalled entries in /etc/portage/package.{,accept_}keywords
No  redundant  entries in /etc/portage/package.mask
No uninstalled entries in /etc/portage/package.mask
No  redundant  entries in /etc/portage/package.unmask
No uninstalled entries in /etc/portage/package.unmask
Skipping check:  redundant  entries in /etc/portage/package.use
Skipping check: uninstalled entries in /etc/portage/package.use
Skipping check:  redundant  entries in /etc/portage/package.env
Skipping check: uninstalled entries in /etc/portage/package.env
No  redundant  entries in /etc/portage/package.license
No uninstalled entries in /etc/portage/package.license
No  redundant  entries in /etc/portage/package.accept_restrict
No uninstalled entries in /etc/portage/package.accept_restrict
Skipping check:  redundant  entries in /etc/portage/package.cflags
Skipping check: uninstalled entries in /etc/portage/package.cflags
All installed versions of packages are in the database.


