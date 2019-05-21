# dokkuVhost
nginx.conf.sigil CORS template

You might not want to change your rest API to support CORS, might be better to do it on the application server.
For Nginx this is done on the nginx.conf
However when deploying an app on Dokku using git, the domain nginx.conf file is recreated, therefore any CORS configuration settings written in the domain conf file will be overwritten.
These are however picked from templates
There are found at
/var/lib/dokku/core-plugins/enabled/nginx-vhosts/templates

To add CORS support, replace your nginx.conf.sigil template with the one in the repo (ofcourse create a backup first)
Rebuild the nginx.conf for your app domain using command below


dokku nginx:build-config <app-name>
  
curl -I -H "Origin: <app-name1>" <app-name2>
