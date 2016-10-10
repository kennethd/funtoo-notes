
	>>> Regenerating /etc/ld.so.cache...
	>>> Original instance of package unmerged safely.
	 *
	 * If you activate the lookup-hostname hook to look up your hostname
	 * using the dns, you need to install net-dns/bind-tools.
	>>> net-misc/dhcpcd-6.11.3 merged.

	 * Messages for package sys-apps/util-linux-2.28.2:

	 * The mesg/wall/write tools have been disabled due to USE=-tty-helpers.

	 * Messages for package dev-db/postgresql-9.6.0:

	 * Unable to find kernel sources at /usr/src/linux
	 * Unable to calculate Linux Kernel version for build, attempting to use running version
	 * Unable to check for the following kernel config options due
	 * to absence of any configured kernel sources or compiled
	 * config:
	 *  - SYSVIPC
	 * You're on your own to make sure they are set if needed.
	 * If you need a global psqlrc-file, you can place it in:
	 *     /etc/postgresql-9.6/
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
	 * http://www.postgresql.org/docs/9.6/static/index.html
	 *
	 * The default location of the Unix-domain socket is:
	 *     /run/postgresql/
	 *
	 * Before initializing the database, you may want to edit PG_INITDB_OPTS
	 * so that it contains your preferred locale in:
	 *     /etc/conf.d/postgresql-9.6
	 *
	 * Then, execute the following command to setup the initial database
	 * environment:
	 *     emerge --config =dev-db/postgresql-9.6.0

	 * Messages for package dev-db/mysql-5.6.33:

	 * MySQL MY_DATADIR is /var/lib/mysql
	 * MySQL datadir found in /var/lib/mysql
	 * A new one will not be created.
	 * If you are upgrading major versions, you should run the
	 * mysql_upgrade tool.

	 * Messages for package net-libs/courier-authlib-0.66.4-r1:

	 * Both gdbm and berkdb selected. Using gdbm.

	 * Messages for package dev-libs/cyrus-sasl-2.1.26-r11:

	 * You need to add a user running a service using Courier's
	 * authdaemon to the 'mail' group. For example, do:
	 *      gpasswd -a postfix mail
	 * to add the 'postfix' user to the 'mail' group.
	 * pwcheck and saslauthd home directories have moved to:
	 *   /run/saslauthd, using tmpfiles.d

	 * Messages for package mail-mta/postfix-3.1.1-r2:

	 * Postfix automatically added to defaut runlevel. To start daemon, run /sbin/rc

	 * Messages for package app-eselect/eselect-php-0.9.2:

	 *
	 * If you are upgrading, be warned that our mod_php configuration
	 * file has changed! You should now define -DPHP for the apache2
	 * daemon, and inspect the new 70_mod_php.conf which has been
	 * installed. Module loading involves eselect as of this version.
	 *
	 * You must run eselect at least once to choose your apache2 target
	 * before the new configuration will work. Afterwards, and after you
	 * have reviewed your new configuration, you are advised to remove
	 * the obsolete 70_mod_php5.conf file.
	 *

	 * Messages for package mail-client/mutt-1.7.0-r5:

	 * The SmartTime functionality has been replaced with
	 * CondDate feature.  To mimic SmartTime, use this CondDate formatter:
	 * %<[12m?%<[7d?%<[12H?%[%H:%M ]&%[%a-%d]>&%[%d-%b]>&%[%b-%y]>

	 * Messages for package app-admin/sudo-1.8.18:

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

	 * Messages for package dev-vcs/git-2.10.0:

	 * These additional scripts need some dependencies:
	 *   git-quiltimport  : dev-util/quilt
	 *   git-instaweb     : || ( www-servers/lighttpd www-servers/apache www-servers/nginx )

	 * Messages for package mail-filter/spamassassin-3.4.1-r8:

	 *
	 * No rules are installed by default. You will need to run sa-update
	 * at least once, and most likely configure SpamAssassin before it
	 * will work.
	 *
	 * You should consider a cron job for sa-update. One is provided
	 * for daily updates if you enable the "cron" USE flag.
	 *
	 * Configuration and update help can be found on the wiki:
	 *
	 *   https://wiki.gentoo.org/wiki/SpamAssassin
	 *

	 * Messages for package dev-libs/glib-2.48.2:

	 * Unable to find kernel sources at /usr/src/linux
	 * Unable to calculate Linux Kernel version for build, attempting to use running version
	 * Unable to check for the following kernel config options due
	 * to absence of any configured kernel sources or compiled
	 * config:
	 *  - INOTIFY_USER
	 * You're on your own to make sure they are set if needed.

	 * Messages for package dev-lang/php-7.0.11-r2:

	 * Installing php.ini for cli into /etc/php/cli-php7.0
	 *
	 * Adding opcache to /etc/php/cli-php7.0/ext
	 * Installing php.ini for apache2 into /etc/php/apache2-php7.0
	 *
	 * Adding opcache to /etc/php/apache2-php7.0/ext
	 *
	 * To enable PHP in apache, you will need to add "-D PHP" to
	 * your apache2 command. OpenRC users can append that string to
	 * APACHE2_OPTS in /etc/conf.d/apache2.
	 *
	 * The apache module configuration file 70_mod_php.conf is
	 * provided (and maintained) by eselect-php.
	 *
	 * To build extensions for this version of PHP, you will need to
	 * add php7-0 to your PHP_TARGETS USE_EXPAND variable.
	 *
	 * This ebuild installed a version of php.ini based on
	 * php.ini-development. You can choose which version of
	 * php.ini to install by default by setting PHP_INI_VERSION
	 * to either 'production' or 'development' in your make.conf.
	 * Both versions of php.ini can be found with the PHP docs in
	 * /usr/share/doc/php-7.0.11-r2
	 *
	 * For details on how version slotting works, please see
	 * the wiki:
	 *
	 *   https://wiki.gentoo.org/wiki/PHP
	 *

	 * Messages for package app-misc/mc-4.8.18:

	 * To enable exiting to latest working directory,
	 * put this into your ~/.bashrc:
	 * . /usr/libexec/mc/mc.sh

	 * Messages for package mail-client/roundcube-1.2.1:

	 * (config) htdocs/config/defaults.inc.php
	 * (info) /var/src/portage/mail-client/roundcube/files/POST-UPGRADE.txt (lang: en)
	 *
	 * The 'vhosts' USE flag is switched ON
	 * This means that Portage will not automatically run webapp-config to
	 * complete the installation.
	 *
	 * To install roundcube-1.2.1 into a virtual host, run the following command:
	 *
	 *     webapp-config -h <host> -d roundcube -I roundcube 1.2.1
	 *
	 * For more details, see the webapp-config(8) man page
	 *
	 * When upgrading from <= 0.9, note that the old configuration files
	 * named main.inc.php and db.inc.php are deprecated and should be
	 * replaced with one single config.inc.php file.
	 *
	 * Run the ./bin/update.sh script to convert those
	 * or manually merge the files.
	 *
	 * The new config.inc.php should only contain options that
	 * differ from the ones listed in defaults.inc.php.
	 *

	 * Messages for package net-misc/dhcpcd-6.11.3:

	 *
	 * If you activate the lookup-hostname hook to look up your hostname
	 * using the dns, you need to install net-dns/bind-tools.

	
	 * Messages for package dev-db/mysql-init-scripts-2.1-r1:

	 * To use the mysql-s6 script, you need to install the optional sys-apps/s6 package.
	 * If you wish to use s6 logging support, comment out the log-error setting in your my.cnf
	 * Starting with version 10.1.8, MariaDB includes an improved systemd unit named mariadb.service
	 * You should prefer that unit over this package's mysqld.service.

	 * Messages for package app-admin/webapp-config-1.54-r2:

	 * webapp-config now requires that all -I/-U/-C commands be followed
	 * by the package name and package version of the webapp
	 * eg.) 'webapp-config -d drupal -I drupal 8.0.0_beta10'
	 * See 'man 8 webapp-config' for more information

