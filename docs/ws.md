## Install Apache as a service
```httpd.exe -k install```

Then run the service
Windows + R -> services.msc

## Restart Apache service
```httpd.exe -k restart```


## 5. .htaccess
Enable authz_groupfile
LoadModule authz_groupfile_module modules/mod_authz_groupfile.so

Create users file in www with htpasswd
Add hugo (pwd: h31*)
```htpasswd -c c:\www\users hugo```

Add celia (pwd: c31*)
```htpasswd c:\www\users celia```

Create groups file in www with htpasswd
Create the file manually with the following content: 
```admin: hugo celia```

To allow .htaccess 
Set in the httpd.conf, in the directory "C:\www":
```AllowOverride All```