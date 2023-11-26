# mariadb-mysql-debian-start-error
Error problem solving, where /etc/mysql/debian-start file not found when installing mariadb-server

so after installing mariadb-server you can get error, when try mariadb-secure-installation / mysql_secure_installation, after checking systemc  status mariadb you will got error:

## Problem
**ExecStartPost=/etc/mysql/debian-start (code=exited, status=203/EXEC)**

**Solution found here:** https://stackoverflow.com/a/51317978

## Solution
**The following command:**

**EDIT** your mariadb-server version mariadb-server-**10.3** if needed (mine was mariadb-server-**10.6**)

apt-get install --reinstall -o Dpkg::Options::="--force-confmiss" mariadb-server-10.3

**Created some files:
**
/etc/mysql/conf.d
/etc/init.d/mysql
/etc/mysql/debian-start

**And:**
apt-get install --reinstall -o Dpkg::Options::="--force-confmiss" mysql-common

**Created:**
/etc/mysql/my.cnf
