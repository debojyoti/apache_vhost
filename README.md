# apache_vhost


# Steps to create virtual hosts on apache in windows

## For first time - follow all the steps and ignore step-2 from next time

## 1) (File-1 : hosts) 
###		Open the following file in Notepad (Run as Administrator)
		
```C:\WINDOWS\system32\drivers\etc\hosts ```


#### Look for the following line at the bottom:

```127.0.0.1   localhost ```

#### Add new localhost domain on a separate line of that file

```127.0.0.2   newsite ```
## (File-2 : httd.conf) 
### 2) Open the main Apache configuration file, httpd.conf (For first time)
		
#### For xampp users,location 

```C:\xampp\apache\conf\httpd.conf ```

#### Comment out the Include... line after Virtual hosts

```
Virtual hosts
Include conf/extra/httpd-vhosts.conf
```



### 3) (File-3 : httpd-vhosts.conf) 
#### Open  extra\httpd-vhosts.conf

For xampp users,location :

```C:\xampp\apache\conf\extra\httpd-vhosts.conf ```

##### i . Remove the hash mark from the beginning of the line
From 
```#NameVirtualHost *.80```
to
```NameVirtualHost *.80	```

##### ii . Add virtual host block in that file (at the end)

```
<VirtualHost *:80>
	  DocumentRoot "C:\xampp\htdocs"
	  ServerName localhost
</VirtualHost>

<VirtualHost *:80>
	  DocumentRoot "C:\xampp\htdocs\newsite"
	  ServerName newsite
</VirtualHost>
```

## Restart apache!
