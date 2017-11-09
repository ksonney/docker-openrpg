OpenRPG running in Docker
=========================

Introduction
------------
I've been running a D&D game for years using OpenRPG. Sadly, 
with every OS upgrade it gets more and more difficult to 
get OpenRPG running with new versions of Python. 

And then I had a revelation - Docker lets me run OpenRPG without
needing to spend hours getting the right (i.e old and cranky)
combination of python and wxPython installed and working. 

Instructions
------------

The easiest thing to do is to install and verify docker on your system, and then :

xhost +
docker run --rm -v /tmp/.X11-unix:/tmp/.X11-unix -v /home/myname/openrpg/myfiles:/openrpg/myfiles -e DISPLAY=unix$DISPLAY ksonney/docker-openrpg

This will use a local myfiles directory (in case you already had data). 
You can omit the myfiles volume if you just want to run the client and connect to a remote game.

