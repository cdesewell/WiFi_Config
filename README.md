he Packages required for the WebGUI are –

lighttpd (I have version 1.4.31-2 installed via apt)
php5-cgi (I have version 5.4.4-12 installed via apt)
along with their supporting packages, php5 will also need to be enabled via the following command and lighttpd restarted.

sudo lighty-enable-mod fastcgi-php
/etc/init.d/lighttpd restart

/etc/sudoers will also need to be updated with the following line –


www-data ALL=(ALL) NOPASSWD:/sbin/ifdown wlan0,/sbin/ifup wlan0,/bin/cat /etc/wpa_supplicant/wpa_supplicant.conf,/bin/cp /tmp/wifidata /etc/wpa_supplicant/wpa_supplicant.conf,/sbin/wpa_cli scan_results,/sbin/wpa_cli scan,/bin/cp /tmp/hostapddata /etc/hostapd/hostapd.conf,/etc/init.d/hostapd start,/etc/init.d/hostapd stop,/etc/init.d/dnsmasq start,/etc/init.d/dnsmasq stop,/bin/cp /tmp/dhcpddata /etc/dnsmasq.conf

Once those modifications are done, unzip the files to /var/www and it should be up and running !
