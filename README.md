
This repo is a collection of notes I kept while setting up [my first Funtoo server](http://kennethd.host.funtoo.org) for hosting virtual mail domains and web sites.

The final notes have been cleaned up to avoid false starts and mistakes made during initial setup, but may not be tested.

Ideally, you can follow along with the pieces you are interested in, because the commands may be taken out of context of my original setup though, it is possible you will run into errors.  If that happens, the log of my original setup of the base system is also available [here](001-install-notes-complete-virtual-mail-server.md), with all of my false starts, mistakes, and corrections documented in chronological order.

  1. [Base System](Base-System.md) Essential packages, intro to *emerge* and *USE* flags
  1. [Virtual Hosts](Virtual-Hosts.md) **vhost** user to own Maildirs and intro to *webapp-config*
  1. [Apache](Apache.md)
  1. [SSL](SSL.md)
  1. [PHP](PHP.md) Postgresadmin, which we use to manage virtual domains, and Dokuwiki both require PHP support
  1. [Postgres](Postgres.md)
  1. [Postfix](Postfix.md) Using Postgres as data store for virtual domains
  1. [Courier IMAP](Courier-IMAP.md) Using Postgres as data store for virtual domains
  1. [Spamassassin and Clamav](Spamassassin-and-Clamav.md)
  1. [Roundcube](Roundcube.md)
  1. [Gitolite](Gitolite.md)
  1. [Dokuwiki](Dokuwiki.md) wiki with *webapp-config* support
  1. [Supervisord](Supervisord.md)
  1. [uWSGI](uWSGI.md)
  1. [Rabbit MQ](Rabbit-MQ.md)
  1. [Mediagoblin](Mediagoblin.md)
  1. [Request Tracker](Request-Tracker.md)

Optional pieces of arch

  * [Nginx](Nginx.md)
  * [MySQL](MySQL.md)
  * [Memcached](Memcached.md)
  * [CouchDb](CouchDb.md)
  * [Redis](Redis.md)
  * [Trac](Trac.md) Issue tracker with *webapp-config* support

