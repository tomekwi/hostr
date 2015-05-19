hostr
=====

[![Join the chat at https://gitter.im/henrytseng/hostr](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/henrytseng/hostr?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

[![Build Status](https://travis-ci.org/henrytseng/hostr.svg?branch=master)](https://github.com/henrytseng/hostr)


Great for testing quick HTML code.  

A simple web server for the current working directory.  Used for hello world style web sites hosting only files in current directory structure.

Serves up files and caches files for quick responses.  

Watches directory structure and refreshes on file changes through LiveReload.  



Installation
------------

Run the following

	npm install hostr -g



Use
----

Run the following command to host the current working directory

	cd project/my_development_project
	hostr
	
A simple web server will be hosted at 

	http://localhost:3000

To host at a different port, set the PORT environment variable (For example, host on port 8080).  

	hostr -p=8080



LiveReload
----------

LiveReload is used for development.  hostr monitors your files.  When a file save occurs LiveReload communicates with your site and pushes a refresh to your browser (e.g. - iPhone/Android/Blackberry, Desktop-Chrome/IE/Safari) so that your changes are immediately visible.  

Communication between hostr and LiveReload occur through WebSockets.  You must use a WebSocket enabled browser.  

To use LiveReload ([additional instructions](http://feedback.livereload.com/knowledgebase/articles/86180-how-do-i-add-the-script-tag-manually-)): 

Add the following code to your HTML:  

	<script>document.write('<script src="http://' + (location.host || 'localhost').split(':')[0] + ':35729/livereload.js?snipver=1"></' + 'script>')</script>

Then run hostr and when file changes are detected your browser will refresh.  

	cd project/my_development_project
	hostr

LiveReload port can be changed (default: 35729), to use port 32021

	hostr -r=32021

To disable LiveReload

	hostr -l=off



Cache
-----

To change cache expiration time (seconds, default: 60)

	host -c=5

To disable watching (debugging only)

	hostr -w=off



Quiet Mode
----------

To run quietly use 

	hostr -q
	
And output will be suppressed


Contribute
----------

If you've got ideas on how to make hostr better create an issue and mark an enhancement in Github.  



License
-------

Copyright (c) 2014 Henry Tseng

Released under the MIT license. See LICENSE for details.