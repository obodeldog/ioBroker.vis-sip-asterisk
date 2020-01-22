# SIP Adapter for ioBroker

Widget to enable SIP communication with asterisk.

## Preparation

### Install Asterisk

Execute the installation script from 'scripts/asterisk':   
./install-asterisk.sh  
-> Enter the IP address of the device   
-> Confirm further actions   

Install the created CA certificate in the browser you will use asterisk with.

The certificate is valid for 800 days. You can use the "renew-asterisk-cert.sh" to renew the certificate.

### Activate HTTPS for ioBroker

Execute the ioBoker certificate script from 'scripts/ioBroker':   
./init-ioBoker-cert.sh  
-> Enter the IP address of the device   

Install the created CA certificate in the browser you will use ioBroker with.

The certificate is valid for 800 days. You can use the "renew-ioBroker-cert.sh" to renew the certificate.

Add the certificate and private key in certificate tab in the ioBroker system view.   

![Certificate tab in the ioBroker system view](img/ioBroker-certs.png)

Configure the Web adapter to activate HTTPS and use the added certificate and private key.

![Web adapter configuration](img/web-adapter-config.png)

## Install the Adapter

Install this adapter in ioBroker and add the widget to your visualization.

## Configure the SIP clients

Open the visualization and enter the follwoing data into the popup:

Private Identity: 1060 or 1061
Public Identity: sip:1060@ipAddress or sip:1061@ipAddress  
Passwort: password   
Anzeigename: arbitrary  
Realm: ipAddress   
Websocket Proxy URL: wss://ipAddress:8089/ws

Use the follwing data for classic SIP clients:

Domain: ipAddress   
Username: 6000 or 6001   
Password: SmartHome!   
Tranport: UDP (Port 5060)   

Replace "ipAddress" with the IP address of your asterisk server.

You can define futher SIP accounts by editing the asterisk configuration (pjsip.conf + extensions.conf)

## More Information

In the doc directory you can find a german documentation which descripes the configuration and installation process and the use with a doorbird door intercom in detail.   
Further information about asterisk can be found on the offical asterisk webpage: wiki.asterisk.org

# Changelog

[Changelog](CHANGELOG.md)

# Licence

MIT License

Copyright 2020 Sebastian Bäumlisberger (https://github.com/sbaeumlisberger) und Sebastian Waldmann (https://github.com/leftstring)

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

