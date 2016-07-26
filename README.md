# prime-acquisition-device
1. 
	D:\SERVER
		|-apache
		|-php

2. APACHE http web server Böngészőben: php.net
   a, apache beszerzése
	http://windows.php.net/download/ 
   jobb oldalt :
	http://www.apachelounge.com/
	FONTOS! 
	Rendszerfüggő (ha nem biztos, akkor 32bit(x86))

  	 downloads link

	C++ Redistributable for Visual Studio 2015: vc_redist_x64/86.exe
	Apache 32 bit:	httpd-2.4.16-win32-VC14.zip   
   a.1, zip-ben az Apache24 kicsomagolása a D:\SERVER\apache-ba
   a.2, a conf könyvtárban lévő httpd.conf megnyitása
	konfigurálása:
	1. szerver helye: 
		ServerRoot "D:/SERVER/apache"
	2. a webes doksik helye D:\www
		DocumentRoot "d:/www"
		<Directory "d:/www">...
   b, apache telepítése rendszerszolgáltatásként
	cmd -> rendszergazdaként
	d: meghajtóra váltás
	d: ENTER
	könyvtár lista
	dir ENTER
	belenavigálunk a D:\SERVER\apache\bin
	cd SERVER
	cd apache
	cd bin
	parancs help
	httpd -?
	telepítés
	httpd -k install 
	indítás
	httpd -k start
	
	grafikusan -> vezérlőpult -> felügyeleti eszközök -> szolgáltatások

    c, a d:\www könyvtárában egy index.html létrehozása
	böngészőben a megtekintés:
	localhost v. 127.0.0.1

3. php beszerzése: php.net
	a, http://windows.php.net/download/
	VC9, VC11 & VC14 résznél a Redistributable for 
	Visual Studio 2012 x86 or x64 telepítése (ez is működik 2015-el)
	PHP 5.6 (5.6.13)
		VC11 x86 Thread Safe
	php-5.6.13-Win32-VC11-x86.zip
	
	b, kicsomagolás a d:\SERVER\php mappába
	
	c, php.ini-development -> php.ini másolata

	d, apache\conf-ban a httpd.conf állomány módosítása a
	php modul betöltéséhez

fájl végéhez írhatóak

# 
LoadModule php5_module "D:/SERVER/php/php5apache2_4.dll"
AddHandler application/x-httpd-php .php

# configure the path to php.ini
PHPIniDir "D:/SERVER/php"

<FilesMatch \.php$>
      SetHandler application/x-httpd-php
</FilesMatch>


valahol a fájlban található
...
<IfModule dir_module>
    DirectoryIndex index.html ->index.php<-
</IfModule>
...
	
	e, apache újraindítása
		grafikusan a szolgáltatásoknál-> újraindít
		konzolban: httpd -k restart

	f, php tesztelése
		index.php állomány a d:\www könyvtárban
		
<?php
	phpinfo();
?>




	böngészőben:
	localhost/index.php v. 127.0.0.1/index.php
	

ezt követően csak Telepíteni kell a C# alkalmazást

 	>"Prime acquisition device"

ha megfelelően hajtotta végre a lépéseket
akkor a minimum és a maximum értékek helyes megadását követően
a "Request Prime" gombra kattintva a "prime" feliratú labellen megjelenik
az igényelt prím szám.
