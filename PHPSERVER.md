// check phps installed
	root@uJohn:~# cd /etc/php
	root@uJohn:/etc/php# ls 
	7.0  7.2  7.3

// switch php version
	-- Disable PHP 7.0
		a2dismod php7.0
	-- Enable PHP 7.2
		a2enmod php7.2
	-- Restart the Apache web server
		systemctl restart apache2

// search installed php extensions
	apt-cache search php7.2



  Problem 1
    - magento/framework 101.0.5 requires ext-mcrypt * -> the requested PHP extension mcrypt is missing from your system.
    - magento/framework 101.0.5 requires ext-mcrypt * -> the requested PHP extension mcrypt is missing from your system.
    - Installation request for magento/framework 101.0.5 -> satisfiable by magento/framework[101.0.5].

  To enable extensions, verify that they are enabled in your .ini files:
    - /etc/php/7.2/cli/php.ini
    - /etc/php/7.2/cli/conf.d/10-mysqlnd.ini
    - /etc/php/7.2/cli/conf.d/10-opcache.ini
    - /etc/php/7.2/cli/conf.d/10-pdo.ini
    - /etc/php/7.2/cli/conf.d/15-xml.ini
    - /etc/php/7.2/cli/conf.d/20-bcmath.ini
    - /etc/php/7.2/cli/conf.d/20-calendar.ini
    - /etc/php/7.2/cli/conf.d/20-ctype.ini
    - /etc/php/7.2/cli/conf.d/20-curl.ini
    - /etc/php/7.2/cli/conf.d/20-dom.ini
    - /etc/php/7.2/cli/conf.d/20-exif.ini
    - /etc/php/7.2/cli/conf.d/20-fileinfo.ini
    - /etc/php/7.2/cli/conf.d/20-ftp.ini
    - /etc/php/7.2/cli/conf.d/20-gd.ini
    - /etc/php/7.2/cli/conf.d/20-gettext.ini
    - /etc/php/7.2/cli/conf.d/20-iconv.ini
    - /etc/php/7.2/cli/conf.d/20-intl.ini
    - /etc/php/7.2/cli/conf.d/20-json.ini
    - /etc/php/7.2/cli/conf.d/20-mbstring.ini
    - /etc/php/7.2/cli/conf.d/20-mysqli.ini
    - /etc/php/7.2/cli/conf.d/20-pdo_mysql.ini
    - /etc/php/7.2/cli/conf.d/20-pdo_sqlite.ini
    - /etc/php/7.2/cli/conf.d/20-phar.ini
    - /etc/php/7.2/cli/conf.d/20-posix.ini
    - /etc/php/7.2/cli/conf.d/20-readline.ini
    - /etc/php/7.2/cli/conf.d/20-shmop.ini
    - /etc/php/7.2/cli/conf.d/20-simplexml.ini
    - /etc/php/7.2/cli/conf.d/20-soap.ini
    - /etc/php/7.2/cli/conf.d/20-sockets.ini
    - /etc/php/7.2/cli/conf.d/20-sqlite3.ini
    - /etc/php/7.2/cli/conf.d/20-sysvmsg.ini
    - /etc/php/7.2/cli/conf.d/20-sysvsem.ini
    - /etc/php/7.2/cli/conf.d/20-sysvshm.ini
    - /etc/php/7.2/cli/conf.d/20-tokenizer.ini
    - /etc/php/7.2/cli/conf.d/20-wddx.ini
    - /etc/php/7.2/cli/conf.d/20-xmlreader.ini
    - /etc/php/7.2/cli/conf.d/20-xmlwriter.ini
    - /etc/php/7.2/cli/conf.d/20-xsl.ini
    - /etc/php/7.2/cli/conf.d/20-zip.ini
  You can also run `php --ini` inside terminal to see which files are used by PHP in CLI mode.
root@uJohn:/var/www/html/crr-revamp-code# 

