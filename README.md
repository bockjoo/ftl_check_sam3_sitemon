# ftl_check_sam3_sitemon
Minimally large effort Emulation of CMS SAM Dashboard in plain cgi/HTML or for failed test alert

[1] How to configuring the script?

In the script, ftl_check_sam3_sitemon.sh, change:

1 inputs

2 notifytowhom

notifytowhom is the crypted email address (Check the pattern)

token.txt is empty in this repo. 

Without the token inside token.txt, the script will fail.

You need to obtain a token to do search https://monit-grafana.cern.ch/api/datasources/proxy/${DBID}/_msearch

from the CMS Monitoring team, Chritian or somebody.

[2] How to cronize?

The following is an example crontab entry

15 * * * * /opt/cms/services/ftl_check_sam3_sitemon.sh > /opt/cms/services/ftl_check_sam3_sitemon.log 2>&1


[3] How to put it on a web server?

cp ftl_check_sam3_sitemon.sh to the web server /cgi-bin/

Point the browser to http://${web_server_hostname}:${port}/cgi-bin/ftl_check_sam3_sitemon.sh to see the old style SAM test dashboard emulation

