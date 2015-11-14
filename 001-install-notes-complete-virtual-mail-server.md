# 2015-11-10 kld

These are notes from the initial install of *kennethd.host.funtoo.org*.

This is my first experience with a Funtoo/Gentoo system, so a lot of rudimentary commands are documented as I learn them.

Install a couple of packages:

    kennethd ~ # emerge app-misc/screen htop sys-process/lsof net-misc/wget net-misc/curl vim

# Funtoo wiki's First Steps page

http://www.funtoo.org/Funtoo_Linux_First_Steps

First things first, make **vi** the default editor.

	kennethd ~ # eselect editor list
	Available targets for the EDITOR variable:
	  [1]   /bin/nano
	  [2]   /usr/bin/ex
	  [3]   /usr/bin/vi
	  [ ]   (free form)
	kennethd ~ # eselect editor set 3
	Setting EDITOR to /usr/bin/vi ...
	!!! Found 2 make.conf files, using both '/etc/make.conf' and '/etc/portage/make.conf'
	Run ". /etc/profile" to update the variable in your shell.

Install a few more fundamental packages, with example output

	kennethd ~ # emerge  --pretend sys-process/glances app-admin/sudo app-portage/eix app-portage/gentoolkit app-misc/mc app-text/wgetpaste net-irc/irssi mail-client/mutt 
	!!! Found 2 make.conf files, using both '/etc/make.conf' and '/etc/portage/make.conf'
	
	These are the packages that would be merged, in order:
	
	Calculating dependencies... done!
	[ebuild  N     ] app-shells/push-1.6 
	[ebuild  N     ] sys-libs/slang-2.3.0  USE="pcre readline zlib -cjk -png -static-libs" ABI_X86="(64) -32 (-x32)" 
	[ebuild   R    ] app-portage/gentoolkit-0.3.0.9-r2 
	[ebuild  N     ] dev-python/psutil-3.2.2  USE="{-test}" PYTHON_TARGETS="python2_7 python3_3 -pypy -python3_4 -python3_5" 
	[ebuild  N     ] app-portage/eix-0.31.3  USE="dep nls -debug -doc -optimization -security -sqlite -strong-optimization -strong-security -swap-remote -tools" LINGUAS="-de -ru" 
	[ebuild  N     ] app-text/wgetpaste-2.25-r3 
	[ebuild  N     ] mail-client/mutt-1.5.24-r2  USE="berkdb crypt gdbm imap nls sasl smtp ssl -debug -doc (-gnutls) -gpg -idn -kerberos -libressl -mbox -nntp -pop -qdbm (-selinux) -sidebar -slang -smime -tokyocabinet" 
	[ebuild  N     ] app-misc/mc-4.8.15  USE="edit nls slang spell xdg -X -gpm -mclib -samba -sftp {-test}" 
	[ebuild  N     ] sys-process/glances-2.4.2  USE="-chart -doc -hddtemp -snmp -web" PYTHON_TARGETS="python2_7 python3_3 -python3_4" 
	[ebuild  N     ] net-irc/irssi-0.8.17  USE="ipv6 perl proxy ssl (-selinux) -socks5" 
	[ebuild  N     ] app-admin/sudo-1.8.15-r1  USE="nls pam sendmail -ldap -offensive (-selinux) -skey" 
	
	 * Messages for package sys-process/glances-2.4.2:
	
	 * Could not find a Makefile in the kernel source directory.
	 * Please ensure that /usr/src/linux points to a complete set of Linux sources
	 * Unable to calculate Linux Kernel version for build, attempting to use running version
	 * Unable to check for the following kernel config options due
	 * to absence of any configured kernel sources or compiled
	 * config:   
	 *  - TASK_IO_ACCOUNTING
	 *  - TASK_DELAY_ACCT
	 *  - TASKSTATS
	 * You're on your own to make sure they are set if needed.
	 * glances can gain additional functionality with following packages:
	 *    dev-python/jinja - export statistics to HTML
	 *    app-admin/hddtemp - monitor hard drive temperatures
	 *    dev-python/pysnmp - enable Python SNMP library support
	 *    dev-python/bottle - for Web server mode
	 *    dev-python/matplotlib - for graphical / chart support
	 * A copy of glances.conf has been added to DOCS
	
	 * Messages for package app-admin/sudo-1.8.15-r1:
	
	 * To use the -A (askpass) option, you need to install a compatible
	 * password program from the following list. Starred packages will
	 * automatically register for the use with sudo (but will not force
	 * the -A option):
	 * 
	 *  [*] net-misc/ssh-askpass-fullscreen
	 *      net-misc/x11-ssh-askpass
	 * 
	 * You can override the choice by setting the SUDO_ASKPASS environmnent
	 * variable to the program you want to use.

Note potential problem about missing linux sources:

	 * Could not find a Makefile in the kernel source directory.
	 * Please ensure that /usr/src/linux points to a complete set of Linux sources

I may also want to remember to install **net-misc/ssh-askpass-fullscreen** provided it is ncurses/not-X

## Create user

The wiki page does not create a user group, but that seems weird to me.  I asked on IRC & apparantly in the Funtoo/Gentoo community both ways are common

kennethd ~ # groupadd kenneth
kennethd ~ # groupadd -r sudo 
kennethd ~ # useradd -m -g kenneth -G wheel,adm,sudo,users kenneth 
kennethd ~ # passwd kenneth

# Gentoo wiki Complete Virtual Mail Server

I will be following directions @ https://wiki.gentoo.org/wiki/Complete_Virtual_Mail_Server
this is my first gentoo/funtoo experience, so first i must learn about USE FLAGS
see https://wiki.gentoo.org/wiki/Handbook:X86/Working/USE

	kennethd ~ # emerge --info | grep ^USE
	USE="acl amd64 berkdb bzip2 cracklib crypt cxx gdbm iconv icu ipv6 mmx modules mudflap multilib ncurses nls nptl openmp pam pcre python readline resolvconf sse sse2 ssl tcpd unicode xattr xml zlib" ABI_X86="64" APACHE2_MODULES="actions alias auth_basic authn_alias authn_anon authn_dbm authn_default authn_file authz_dbm authz_default authz_groupfile authz_host authz_owner authz_user autoindex cache cgi cgid dav dav_fs dav_lock deflate dir disk_cache env expires ext_filter file_cache filter headers include info log_config logio mem_cache mime mime_magic negotiation rewrite setenvif speling status unique_id userdir usertrack vhost_alias authn_core authz_core socache_shmcb unixd" CALLIGRA_FEATURES="kexi words flow plan sheets stage tables krita karbon braindump author" CAMERAS="ptp2" COLLECTD_PLUGINS="df interface irq load memory rrdtool swap syslog" CPU_FLAGS_X86="aes mmx mmxext popcnt sse sse2 sse3 sse4_1 sse4_2 ssse3" ELIBC="glibc" GPSD_PROTOCOLS="ashtech aivdm earthmate evermore fv18 garmin garmintxt gpsclock itrax mtk3301 nmea ntrip navcom oceanserver oldstyle oncore rtcm104v2 rtcm104v3 sirf superstar2 timing tsip tripmate tnt ublox ubx" GRUB_PLATFORMS="efi-64 pc" INPUT_DEVICES="evdev synaptics keyboard mouse" KERNEL="linux" LCD_DEVICES="bayrad cfontz cfontz633 glk hd44780 lb216 lcdm001 mtxorb ncurses text" LIBREOFFICE_EXTENSIONS="presenter-console presenter-minimizer" OFFICE_IMPLEMENTATION="libreoffice" PHP_TARGETS="php5-5" PYTHON_ABIS="2.7 3.3" PYTHON_SINGLE_TARGET="python3_3" PYTHON_TARGETS="python2_7 python3_3" QEMU_SOFTMMU_TARGETS="i386 x86_64" QEMU_USER_TARGETS="i386 x86_64" RUBY_TARGETS="ruby20 ruby21 ruby22" USERLAND="GNU" XTABLES_ADDONS="quota2 psd pknock lscan length2 ipv4options ipset ipp2p iface geoip fuzzy condition tee tarpit sysrq steal rawnat logmark ipmark dhcpmac delude chaos account"

OK.  The recommended installation includes Apache + PHP, I will have to remember to review the PHP "uses" later (equery uses php) -- enable cli + readline

according to https://wiki.gentoo.org/wiki/Complete_Virtual_Mail_Server/System_Setup_and_Packages
it looks like we need to add USE entries for apache2 imap postgres (and because i still have services on my old server that use both) mysql

	kennethd ~ # cp /etc/portage/make.conf.example /etc/portage/make.conf
	kennethd ~ # vim /etc/portage/make.conf

edit USE variable to:

	USE="-X -alsa -gnome -gtk -kde -qt4 apache2 imap mysql postgres"

check to see if it changed anything (within screen session):

	kennethd ~ # emerge --update --deep --newuse @world

something like 22 packages were rebuilt.  next, check for newly obsoleted packages

	kennethd ~ # emerge -p depclean

	>>> These are the packages that would be unmerged:
	
	 sys-fs/mdadm
		selected: 3.3.4 
	   protected: none
		 omitted: none
	
	 sys-fs/cryptsetup
		selected: 1.6.7 
	   protected: none
		 omitted: none
	
	 sys-fs/lvm2
		selected: 2.02.111 
	   protected: none
		 omitted: none
	
	 sys-block/thin-provisioning-tools
		selected: 0.5.3 
	   protected: none
		 omitted: none
	
	 dev-libs/boost
		selected: 1.57.0 
	   protected: none
		 omitted: none
	
	 dev-util/boost-build
		selected: 1.57.0 
	   protected: none
		 omitted: none

it looks weird to remove mdadm & lvm2, but this is a simfs filesystem:

	Disk:
	------------------------------------
	
	  Partitioning:
	  --------------------
		
	
	  Mount table:
	  --------------------
		
		proc /proc proc defaults 0 0
	
	  Mounted partitions:
	  --------------------
		
			/dev/simfs / simfs rw,relatime 0 0
			/dev/simfs /var/src/portage simfs ro,relatime 0 0
			proc /proc proc rw,relatime 0 0
			sysfs /sys sysfs rw,relatime 0 0
			tmpfs /run tmpfs rw,nodev,relatime,size=4943592k,mode=755 0 0
			dev /dev devtmpfs rw,nosuid,relatime,size=10240k,mode=755 0 0
			mqueue /dev/mqueue mqueue rw,nosuid,nodev,noexec,relatime 0 0
			devpts /dev/pts devpts rw,nosuid,noexec,relatime,gid=5,mode=620,ptmxmode=000 0 0
			shm /dev/shm tmpfs rw,nosuid,nodev,noexec,relatime 0 0
			cgroup_root /sys/fs/cgroup tmpfs rw,nosuid,nodev,noexec,relatime,size=10240k,mode=755 0 0
			blkio /sys/fs/cgroup/blkio cgroup rw,nosuid,nodev,noexec,relatime,blkio,name=beancounter 0 0
			memory /sys/fs/cgroup/memory cgroup rw,nosuid,nodev,noexec,relatime,memory 0 0
	
	  Free space:
	  --------------------
		
			Filesystem       1K-blocks      Used Available Use% Mounted on
			/vz/private/2107 209715200   1633380 208081820   1% /
			/usr/portage     910200448 237361860 626596440  28% /var/src/portage
			tmpfs              4943592        52   4943540   1% /run
			dev                  10240         0     10240   0% /dev
			shm               24717944         0  24717944   0% /dev/shm
			cgroup_root          10240         4     10236   1% /sys/fs/cgroup


	kennethd ~ # revdep-rebuild 
	!!! Found 2 make.conf files, using both '/etc/make.conf' and '/etc/portage/make.conf'
	 * Configuring search environment for revdep-rebuild
	 * Unable to find a satisfactory location for temporary files (/var/cache/revdep-rebuild)

This message is a Funtoo JIRA ticket: https://bugs.funtoo.org/browse/FL-1793

	kennethd ~ # mkdir /var/cache/revdep-rebuild
	kennethd ~ # revdep-rebuild
	kennethd ~ # emerge --ask dev-lang/php
	kennethd ~ # emerge --sync
	!!! Found 2 make.conf files, using both '/etc/make.conf' and '/etc/portage/make.conf'
	>>> Syncing repository 'gentoo' into '/var/src/portage'...
	/usr/bin/git pull
	error: cannot open .git/FETCH_HEAD: Read-only file system

That's expected on the hosted Funtoo.org containers.

	!!! git pull error in /var/src/portage
	!!! Found 2 make.conf files, using both '/etc/make.conf' and '/etc/portage/make.conf'
	kennethd ~ # emerge -uDNva @world
	!!! Found 2 make.conf files, using both '/etc/make.conf' and '/etc/portage/make.conf'
	
	These are the packages that would be merged, in order:
	
	Calculating dependencies... done!
	
	Total: 0 packages, Size of downloads: 0 KiB
	
	Nothing to merge; quitting.

## Emerge the full list of packages

There is a note at the end of the page that you should be able to get away with installing a single package if you configure your USEs correctly, naturally I didn't read that far ahead.

	kennethd ~ # emerge app-admin/webmin www-apps/postfixadmin mail-client/roundcube www-misc/awstats dev-db/postgresql dev-db/mysql net-mail/courier-imap net-libs/courier-authlib dev-libs/cyrus-sasl mail-filter/amavisd-new mail-filter/spamassassin app-antivirus/clamav mail-mta/postfix mail-filter/gld

### Setting package-specific USE vars

Here we get to learn a little about the *package.use* system

	The following USE changes are necessary to proceed:
	 (see "package.use" in the portage(5) man page for more details)
	# required by media-gfx/graphviz-2.38.0-r1::gentoo
	# required by dev-perl/GraphViz-2.180.0::gentoo
	# required by net-dns/dnssec-tools-2.1::gentoo
	# required by app-admin/webmin-1.760::gentoo
	# required by app-admin/webmin (argument)
	>=media-libs/gd-2.1.1-r1 truetype jpeg png fontconfig
	# required by mail-client/roundcube-1.0.6::gentoo
	# required by mail-client/roundcube (argument)
	>=dev-lang/php-5.5.30 pdo sockets
	
	Use --autounmask-write to write changes to config files (honoring
	CONFIG_PROTECT). Carefully examine the list of proposed changes,
	paying special attention to mask or keyword changes that may expose
	experimental or unstable packages.

Without researching what *--autounmask-write* does, I thought perhaps it would just take care of the USE changes for me

	kennethd ~ # emerge --autounmask-write app-admin/webmin www-apps/postfixadmin mail-client/roundcube www-misc/awstats dev-db/postgresql dev-db/mysql net-mail/courier-imap net-libs/courier-authlib dev-libs/cyrus-sasl mail-filter/amavisd-new mail-filter/spamassassin app-antivirus/clamav mail-mta/postfix mail-filter/gld

Unfortunately, it doesn't work that way.  IIRC it complained about missing files &/or directories.

	kennethd ~ # mkdir /etc/portage/package.use/dev-lang
	kennethd ~ # mkdir /etc/portage/package.use/media-libs
	kennethd ~ # touch /etc/portage/package.use/dev-lang/php-5.5.30
	kennethd ~ # touch /etc/portage/package.use/media-libs/gd-2.1.1-r1

Trying again

	The following USE changes are necessary to proceed:
	 (see "package.use" in the portage(5) man page for more details)
	# required by media-gfx/graphviz-2.38.0-r1::gentoo
	# required by dev-perl/GraphViz-2.180.0::gentoo
	# required by net-dns/dnssec-tools-2.1::gentoo
	# required by app-admin/webmin-1.760::gentoo
	# required by app-admin/webmin (argument)
	>=media-libs/gd-2.1.1-r1 truetype jpeg png fontconfig
	# required by mail-client/roundcube-1.0.6::gentoo
	# required by mail-client/roundcube (argument)
	>=dev-lang/php-5.5.30 pdo sockets
	
	Autounmask changes successfully written.
	
	 * IMPORTANT: config file '/etc/portage/package.use/media-libs/gd-2.1.1-r1' needs updating.
	 * See the CONFIGURATION FILES section of the emerge
	 * man page to learn how to update config files.

### Config file needs updating

This message is essentially a merge conflict.  There are changes and a human is required to review them.  Resolution is indicated simply by getting rid of the *._cfgXXXX_* version

	kennethd ~ # mv /etc/portage/package.use/media-libs/._cfg0000_gd-2.1.1-r1 /etc/portage/package.use/media-libs/gd-2.1.1-r1

### Ready for a Successful emerge

	kennethd ~ # time emerge --update  app-admin/webmin www-apps/postfixadmin mail-client/roundcube www-misc/awstats dev-db/postgresql dev-db/mysql net-mail/courier-imap net-libs/courier-authlib dev-libs/cyrus-sasl mail-filter/amavisd-new mail-filter/spamassassin app-antivirus/clamav mail-mta/postfix mail-filter/gld

59 minutes later...

### Revisit USE flags again

	kennethd ~ # vim /etc/portage/make.conf

edit USE variable to:

	USE="-X -alsa -gnome -gtk -kde -mbox -qt4 -vda apache2 authdaemond bzip2 clamdtop crypt geoip imap ipv6 maildir mysql postgres sasl spamassassin spell ssl urandom vhosts"

check to see if it changed anything (within screen session):

	kennethd ~ # emerge --update --deep --newuse @world

curl is now missing as a php requirement, update package.use tree:

	kennethd ~ # for f in `ls -1  /etc/portage/package.use/*/*` ; do echo -e "\n$f:\n"; cat $f ; done 
	
	/etc/portage/package.use/dev-lang/php-5.5.30:
	
	# required by mail-client/roundcube-1.0.6::gentoo[spell]
	# required by @selected
	# required by @world (argument)
	>=dev-lang/php-5.5.30 curl
	# required by mail-client/roundcube-1.0.6::gentoo
	# required by mail-client/roundcube (argument)
	>=dev-lang/php-5.5.30 pdo sockets
	
	/etc/portage/package.use/media-libs/gd-2.1.1-r1:
	
	# required by media-gfx/graphviz-2.38.0-r1::gentoo
	# required by dev-perl/GraphViz-2.180.0::gentoo
	# required by net-dns/dnssec-tools-2.1::gentoo
	# required by app-admin/webmin-1.760::gentoo
	# required by app-admin/webmin (argument)
	>=media-libs/gd-2.1.1-r1 truetype jpeg png fontconfig

12 packages are built or re-built due to the USE changes

	 * IMPORTANT: config file '/etc/mysql/my.cnf' needs updating.
	 * See the CONFIGURATION FILES section of the emerge
	 * man page to learn how to update config files.
	 * After world updates, it is important to remove obsolete packages with
	 * emerge --depclean. Refer to `man emerge` for more information.
	kennethd ~ # ls -lA /etc/mysql/
	total 12
	-rw-r--r-- 1 root root 3916 Nov 11 19:35 ._cfg0000_my.cnf
	-rw-r--r-- 1 root root 3967 Nov 11 15:01 my.cnf
	-rw-r--r-- 1 root root 1702 Nov 11 19:35 mysqlaccess.conf
	kennethd ~ # diff /etc/mysql/my.cnf /etc/mysql/._cfg0000_my.cnf 
	98d97
	< #innodb_log_arch_dir          = /var/lib/mysql/
	142,143d140
	< 
	< [mariadb]
	kennethd ~ # mv /etc/mysql/._cfg0000_my.cnf /etc/mysql/my.cnf 

### check again for newly obsoleted packages:

	kennethd ~ # emerge -p --depclean
	
	>>> These are the packages that would be unmerged:
	
	 dev-lang/nasm
		selected: 2.11.08 
	   protected: none
		 omitted: none
	
	 virtual/perl-Term-ANSIColor
		selected: 4.30.0 
	   protected: none
		 omitted: none

looks safe enough, do that again with out the -p

# Create vmail user

https://wiki.gentoo.org/wiki/Complete_Virtual_Mail_Server/Linux_vmail_user

	kennethd ~ # groupadd -g 5000 vmail 
	kennethd ~ # useradd -m -d /var/vmail -s /bin/false -u 5000 -g vmail vmail
	kennethd ~ # ls -ld /var/vmail/
	drwxr-xr-x 3 vmail vmail 4096 Nov 11 22:39 /var/vmail/
	kennethd ~ # chown vmail:vmail /var/vmail/
	kennethd ~ # chmod 2770 /var/vmail/
	kennethd ~ # ls -ld /var/vmail
	drwxrws--- 3 vmail vmail 4096 Nov 11 22:39 /var/vmail

Make postfix aware of the vmail user

	kennethd ~ # vim /etc/postfix/main.cf

these are new options to this file, append them to the end

	# 2015-11-11 kld https://wiki.gentoo.org/wiki/Complete_Virtual_Mail_Server/Linux_vmail_user
	# Link the mailbox uid and gid to postfix.
	virtual_uid_maps = static:5000
	virtual_gid_maps = static:5000
	# Set the base address for all virtual mailboxes
	virtual_mailbox_base = /var/vmail

# Admin Support Systems

https://wiki.gentoo.org/wiki/Complete_Virtual_Mail_Server/Admin_Support_Systems

Make sure Apache & PHP are working OK  https://wiki.gentoo.org/wiki/Apache

	kennethd ~ # emerge --ask www-apache/mod_security
	!!! Found 2 make.conf files, using both '/etc/make.conf' and '/etc/portage/make.conf'
	
	These are the packages that would be merged, in order:
	
	Calculating dependencies... done!
	[ebuild  N     ] www-apache/mod_security-2.7.7  USE="geoip -curl -jit -lua" 
	[ebuild  N     ] www-apache/modsecurity-crs-2.2.7  USE="geoip -lua" 

Enable the SECURITY module in the apache2 file's APACHE2_OPTS variable by adding `APACHE2_OPTS="... -D SECURITY -D PHP5"`

	APACHE2_OPTS="-D DEFAULT_VHOST -D INFO -D SSL -D SSL_DEFAULT_VHOST -D LANGUAGE -D SECURITY -D PHP5"

## missing GeoIP.dat

Apache won't start due to a missing GeoIP.dat file

	08:51 < kennethd> Hi, I am following along with
		https://wiki.gentoo.org/wiki/Complete_Virtual_Mail_Server &
		https://wiki.gentoo.org/wiki/Apache but when I try to start apache I get: Could
		not open geo database "/usr/share/GeoIP/GeoIP.dat": No such file or directory.
		Is there something like 'apt-file search' I can use to see what provides this
		file?
	08:55 <@angry_vincent> kennethd: qfile /usr/share/GeoIP/GeoIP.dat
	08:58 < kennethd> angry_vincent: thanks! exactly what I was looking for. unfortunately it returns nothing, but good to know.  I'll just remove geoip from USE for now
	09:01 <@angry_vincent> kennethd: then, a package installing this file not really installed
	09:01 <@angry_vincent> kennethd: i don't remember name, but with use geoip it should pull the package
	09:01 <@angry_vincent> kennethd: in theory
	09:07 <+_`_> don't think that file is owned by the dev-libs/geoip package, seems it's generated by geoipupdate.sh which is owned by it.
	09:08 <+_`_> seems you're expected to run that post install to initially populate /usr/share/GeoIP/
	09:09 < kennethd> angry_vincent: I see, qfile only searches files installed on system, not all files installable via your portage tree. thanks!  So if I want to know what
					  package provides say /usr/bin/locate, what is the best tool to use to find out?
	09:10 < kennethd> +_`_: I see, thanks.  I probably missed a post-install note after installing a bunch of packages
	09:10 <+_`_> there's no truly deterministic way of doing that because of source nature
	09:10 <+_`_> http://www.portagefilelist.de/
	09:10 <+_`_> there's that but yeah
	09:10 <@angry_vincent> kennethd: package content is not provided, because of source-based
	09:11 <+_`_> to answer your exact question
	09:11 <@angry_vincent> kennethd: highly dependant on how you install package (via USE)
	09:11 <+_`_> but you'd ideally search for packages based on description/name
	09:11 < kennethd> Ah, makes sense
	09:14 <+_`_> seems locate on other distributions is usually mlocate, which is packaged in sys-apps/mlocate

After removing `geoip` from my USE config and re-emerging apache2 starts fine, but ok, we have a potential solution, so one more try.

re-add geoip to USE in /etc/portage/make.conf

	kennethd ~ # emerge sys-apps/mlocate
	kennethd ~ # emerge Geo-IP

Might as well try to add the PHP extension as well

	kennethd ~ # pecl install geoip
	
	Installing '/usr/lib64/php5.5/lib/extensions/no-debug-non-zts-20121212/geoip.so'
	install ok: channel://pecl.php.net/geoip-1.0.8
	configuration option "php_ini" is not set to php.ini location
	You should add "extension=geoip.so" to php.ini
	kennethd ~ # locate php.ini
	/etc/php/apache2-php5.5/php.ini
	/etc/php/cli-php5.5/php.ini
	/usr/share/doc/php-5.5.30/php.ini-development.bz2
	/usr/share/doc/php-5.5.30/php.ini-production.bz2
	kennethd ~ # grep geoip /etc/php/apache2-php5.5/php.ini
	kennethd ~ #

still nothing, turn it off again..  move on to Postgres

# PostgreSQL

https://wiki.gentoo.org/wiki/PostgreSQL

	kennethd ~ # psql -U postgres -d postgres
	psql: could not connect to server: No such file or directory
			Is the server running locally and accepting
			connections on Unix domain socket "/run/postgresql/.s.PGSQL.5432"?
	kennethd ~ # /etc/init.d/postgresql-9.4 start
	 * Directory not found: /var/lib/postgresql/9.4/data
	 * HINT: Ensure that DATA_DIR points to the right path.
	 * HINT: Or perhaps you need to create the database cluster:
	 *     emerge --config dev-db/postgresql:9.4
	 * ERROR: postgresql-9.4 failed to start

## emerge --config

	kennethd ~ # emerge --config dev-db/postgresql:9.4
	!!! Found 2 make.conf files, using both '/etc/make.conf' and '/etc/portage/make.conf'
	
	Configuring pkg...
	
	 * You can modify the paths and options passed to initdb by editing:
	 *     /etc/conf.d/postgresql-9.4
	 *
	 * Information on options that can be passed to initdb are found at:
	 *     http://www.postgresql.org/docs/9.4/static/creating-cluster.html
	 *     http://www.postgresql.org/docs/9.4/static/app-initdb.html
	 *
	 * PG_INITDB_OPTS is currently set to:
	 *     --encoding=UTF8
	 *
	 * Configuration files will be installed to:
	 *     /etc/postgresql-9.4/
	 *
	 * The database cluster will be created in:
	 *     /var/lib/postgresql/9.4/data
	 *
	 * Are you ready to continue? (y/n)
	y
	 * Creating the data directory ...
	 * Initializing the database ...
	The files belonging to this database system will be owned by user "postgres".
	This user must also own the server process.
	
	The database cluster will be initialized with locales
	  COLLATE:  C
	  CTYPE:    en_US.UTF-8
	  MESSAGES: C
	  MONETARY: en_US.UTF-8
	  NUMERIC:  en_US.UTF-8
	  TIME:     en_US.UTF-8
	The default text search configuration will be set to "english".

And it starts...

	kennethd ~ # /etc/init.d/postgresql-9.4 start
	 * /run/postgresql: creating directory
	 * /run/postgresql: correcting owner
	 * Starting PostgreSQL ...  [ ok ]

Try it out

	kennethd ~ # psql -U postgres -d postgres
	psql (9.4.5)
	Type "help" for help.
	
	postgres=# CREATE ROLE kenneth WITH LOGIN;
	CREATE ROLE
	postgres=# \password kenneth
	Enter new password: 
	Enter it again: 
	postgres=# CREATE DATABASE testdb WITH OWNER kenneth;
	CREATE DATABASE
	postgres=# \l
									List of databases
	   Name    |  Owner   | Encoding | Collate |    Ctype    |   Access privileges   
	-----------+----------+----------+---------+-------------+-----------------------
	 postgres  | postgres | UTF8     | C       | en_US.UTF-8 | 
	 template0 | postgres | UTF8     | C       | en_US.UTF-8 | =c/postgres          +
			   |          |          |         |             | postgres=CTc/postgres
	 template1 | postgres | UTF8     | C       | en_US.UTF-8 | =c/postgres          +
			   |          |          |         |             | postgres=CTc/postgres
	 testdb    | kenneth  | UTF8     | C       | en_US.UTF-8 | 
	(4 rows)


# Postfix and Postgres Integration

https://wiki.gentoo.org/wiki/Complete_Virtual_Mail_Server/Postfix_to_Database

	kennethd ~ # createuser -U postgres -D -P -R -S postfix
	Enter password for new role: 
	Enter it again: 

## Set per-package USE vars

	kennethd ~ # mkdir /etc/portage/package.use/mail-mta
	kennethd ~ # echo "mail-mta/postfix cdb hardened postgres sasl ssl" >>  /etc/portage/package.use/mail-mta/postfix
	kennethd ~ # emerge --ask postfix
	
	>>> Installing (2 of 2) mail-mta/postfix-3.0.1-r1::gentoo
	 * >>> SetGID: [chmod o-r] /usr/sbin/postdrop ... [ ok ]
	 * >>> SetGID: [chmod o-r] /usr/sbin/postqueue ... [ ok ]
	 * Correcting permission of spool directory
	 * Auto-adding 'postfix' service to your default runlevel
	 * Postfix automatically added to defaut runlevel. To start daemon, run /sbin/rc
	
	 * Messages for package mail-mta/postfix-3.0.1-r1:
	
	 * Correcting permission of spool directory
	 * Postfix automatically added to defaut runlevel. To start daemon, run /sbin/rc
	>>> Auto-cleaning packages...
	
	>>> No outdated packages were found on your system.
	
	 * GNU info directory index is up-to-date.
	
	 * IMPORTANT: config file '/etc/postfix/main.cf' needs updating.
	 * See the CONFIGURATION FILES section of the emerge
	 * man page to learn how to update config files.

## Examine config changes

	kennethd ~ # diff /etc/postfix/main.cf /etc/postfix/._cfg0000_main.cf 
	680,689d679
	< 
	< 
	< # 2015-11-11 kld https://wiki.gentoo.org/wiki/Complete_Virtual_Mail_Server/Linux_vmail_user
	< # Link the mailbox uid and gid to postfix.
	< virtual_uid_maps = static:5000
	< virtual_gid_maps = static:5000
	< # Set the base address for all virtual mailboxes
	< virtual_mailbox_base = /var/vmail
	< 
	< 
	kennethd ~ # rm /etc/postfix/._cfg0000_main.cf 

## Re-emerge postfixadmin

Continuing with the instructions above, a user & db schema is missing.  Re-emerging postfixadmin reveals a step I missed:

	kennethd ~ # emerge postfixadmin
	 * Messages for package www-apps/postfixadmin-2.3.8:
	
	 * (config) htdocs/config.inc.php
	 * (info) /var/src/portage/www-apps/postfixadmin/files/postinstall-en-2.3.txt (lang: en)
	 * 
	 * The 'vhosts' USE flag is switched ON
	 * This means that Portage will not automatically run webapp-config to
	 * complete the installation.
	 * 
	 * To install postfixadmin-2.3.8 into a virtual host, run the following command:
	 * 
	 *     webapp-config -h <host> -d postfixadmin -I postfixadmin 2.3.8
	 * 
	 * For more details, see the webapp-config(8) man page

`man 8 webapp-config` is worth reading.  It looks like a nice system, definitely a pleasant surprise (I wonder how I'd never heard of it), but it will be a new set of conventions to pick up along the way.

## Create vhost user & HOME

First, I imagine the domain & domain owner user account must be created before I can create the postfix database for the domain.

Some studying: https://wiki.gentoo.org/wiki/Webapp-config Summarizes webapp-config very well, but offers little in terms of practical getting started info.

http://gentoovps.net/webapp-config/ looks like it will fill in some of the practical HOWTO stuff.  It immediately refers us to http://gentoovps.net/apache-vhost/

I disagree with that guy about the fqdn thing; I prefer a structure that allows for a dedicated user for each domain, regardless of number of subdomains;

	/vhosts 						root:root drwx--x--x
		/highball.org				highball:highball ($HOME) drwxr-xr-x
			/bin					user's $HOME/bin
			/etc					user configs
			/var					user data
			/ftp					ftp root, if necessary (for example)
			/www					per-subdomain directories...
				/etc				site configs
				/htdocs				apache DOCUMENT_ROOT
				/venv				python virtualenv (for example, whatever resources a www release needs)
			/qa						more subdomains...
			/trac					trac webapp
			/wiki					dokuwiki webapp



