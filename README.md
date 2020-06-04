# A simple script to log the deletion process of files

This is my first time creating a repository for a project and i did want to put something simple

## Purpose
The purpose of this simple shell script is to log the deletion process of files in the simplest way possible

## Pre-requisites
you'll first need the logger utility That is to sned logs to the syslog daemeon.
I tested this script with Rsyslog and it will also work with other logging system that use syslog protocol
and you may need to adjust your system logging configuration because this script uses the ```user.notice``` severity/priority

this is what i needed to configure on my system
```
$ echo "user.notice   /var/log/del.log" >> /etc/rsyslog.conf
```
## Usage
I use this script as a wrapper , instead of calling rm i call this script and let it log the event and then  call rm to remove the file.
