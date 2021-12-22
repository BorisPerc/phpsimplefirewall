# phpsimplefirewall
Simple PHP Firewall

install app instructions:

download file and unpack it to your root webserver directory example:

/home/www/htdocs/index.php   or    /var/www/html/index.php   ecc... upload from your FTP server to domain or subdomain of your web app this simple script and activate it by puting in index.php file of your webapp this directives:

<?php 
define('PHP_FIREWALL_REQUEST_URI', strip_tags( $_SERVER['REQUEST_URI'] ) );
define('PHP_FIREWALL_ACTIVATION', true );
if ( is_file( @dirname(__FILE__).'/enigma/firewall.php' ) )
	include_once( @dirname(__FILE__).'/enigma/firewall.php' );

/**
 * Your web apps scripts index.php
 * PS this script is blocking only some IPs and you can code your custom ips to block very easy
 */

When you will unzip the program the mail directory and log files will be in /enigma/ directory of your vHost or php based web app
All settings you can change in firewall.php file, put your allow ips ecc.....

