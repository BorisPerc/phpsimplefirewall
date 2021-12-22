# phpsimplefirewall
Simple PHP Firewall

install app instructions:

download file and unpack it to your root webserver directory example:

/home/www/htdocs/index.php   or    /var/www/html/index.php   ecc... upload from your FTP server to domain or subdomain of your web app this simple script and activate it by puting in index.php file of your webapp this directives:

<  ?    php 

	define('PHP_FIREWALL_REQUEST_URI', strip_tags( $_SERVER['REQUEST_URI'] ) );

	define('PHP_FIREWALL_ACTIVATION', true );

	if ( is_file( @dirname(__FILE__).'/enigma/firewall.php' ) )

	include_once( @dirname(__FILE__).'/enigma/firewall.php' );
	

 after upper code here are your web apps scripts index.php
PS this script is blocking only some IPs and you can code your custom ips to block very easy undesidered networks to access your web app based on php/SQL 


When you will unzip the program the mail directory and log files will be in /enigma/ directory of your vHost or php based web app
All settings you can change in firewall.php file, put your allow ips ecc.....

For configure Allow ips you set up this in sample firewall.php file from line 37 to 46:

/** IPS PROTECTED  Allow ips for deny you put return code deny!!! */

	if ( count( $IP_ALLOW ) > 0 ) {
	if ( in_array( $_SERVER['REMOTE_ADDR'], $IP_ALLOW ) ) return;
	}

	if ( $_SERVER["REMOTE_ADDR"] == '192.168.0.1' ) {
 	return 'ALLOW'; 
 	}
 
	$ip_array = array( '1.1.1.1' , '1.0.0.1' , '8.8.8.8' , '8.8.4.4' , '1.2.3.4' , '5.6.7.8' , '12.34.56.78' );
	if ( in_array( $_SERVER["REMOTE_ADDR"], $ip_array ) ) {
	return 'ALLOW'; 
	}

/** END IPS PROTECTED */


PS: Do not forget to change permition to 777 for logs file in directory /enigma/ if you don`t do this log file will not be able to write blocked ips!!!

instructions are in readme simple php firewall.txt = enigmaphpfw.zip



