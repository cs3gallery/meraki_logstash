Meraki MX Series Logstash Configurations

Works and tested with Logstash v1.5.*

This will monitor all your Events, IDS, Flows, and URL Syslog information.


I started this project because I could not find anything out their that was up to date and had what I was looking
for. I wanted to make something that was easy to configure, read, and understand. This project will continually be updated by me and
any contributor who feels like joining in.

This project includes configurations for a full working setup using syslog-ng for capturing and parsing flows, events, urls, and ids_alerts into their own separate log files to be sent later to logstash via the logstash forwarder. Obviously you don't have to use these configurations and use whatever you would like if you know what you are doing :)

########################################
#
#  Install
#
########################################


1. make sure you have syslog-ng installed to receive log files.

2. copy syslog-ng/conf.d/meraki.conf to /etc/syslog-ng/conf.d/ (Or wherever else you may have set it up.)

3. make sure logstash-forwarder is installed to ship your logs to logstash

4. cp logstash-forwarder/logstash-forwarder.yml to /etc/ (Make sure you edit the fields to connect to your logstash server.)

5. On your logstash server copy /logstash/*.conf files to your logstash configurations normally located in /etc/logstash/cond.d (Rename them to any order you deem good.) I just kept mine at 10-, 11-, 12-, 13-, etc.

6. cp logstash/patterns folder to your logstash configuration root directory normally located in /etc/logstash

7. cp /logstash/GeoLiteCity.dat to your logstash configuration root directory as well

8. Restart your logstash server and all should be good :)



If you want to help but cannot script please post the strings that come in with errors or ones not being parsed and I can add them in. Thanks!!