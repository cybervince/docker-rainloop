[![](https://badge.imagelayers.io/krishath/rainloop-ssl:latest.svg)](https://imagelayers.io/?images=krishath/rainloop-ssl:latest 'Get your own badge on imagelayers.io')

Docker Rainloop
=============

Rainloop web client Docker image using nginx (SSL).

How to use
-------

	docker pull krishath/rainloop-ssl
	docker run -d --name rainloop -v certfolder:/etc/ssl -h rainloop -p 443:443 krishath/rainloop

Open your browser and visit 
	
	https://127.0.0.1

SSL
---
Mount your host folder containing your cert && key to `/etc/ssl`.
Name (or link) them as `cert.key` and `cert.pem`.

Data Persistance
----------------
Mount your data folder to `/webapps/rainloop/data`.


docker-compose example config:
------------------------------

	webmail:
	  image: "krishath/rainloop-ssl"
	  volumes:
	   - ./webmail/ssl:/etc/ssl
	   - ./webmail/data:/webapps/rainloop/data
	  ports:
	    - "9000:443"


License
-------

Apache 2 http://en.wikipedia.org/wiki/Apache_License

Credits
-------

I've initially modified the Dockerfile of [ahmet2mir](https://github.com/ahmet2mir).
