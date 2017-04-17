#borgbackup

[Borgbackup](https://borgbackup.readthedocs.io) is a deduplicating backup system. After install this script 
will make backups for you. Run as root.

## Useage

Set up Python 3 virtual local environment to be used and invoked by root, and which will be in turn used to install and run the borg-backup script. This is a way to ensure the Python environment consistently meets requirements, so you could approach this step in different ways if you wanted to. The [borgbackup install docs](http://borgbackup.readthedocs.io/en/stable/installation.html) provide the necessary steps for different operating systems.

Modify .borg.env and paths in script to meet your needs. Copy .borg.env to /root. Copy the script to /etc/cron.daily and ensure executable. 

Use the commented commands to initialize your repositories, test and use!

## Off site copy?

A command like ``rsync -ra source destination`` will make a copy of the repo which could be on an external destination for off-site storage.

## RHEL6 install notes

Installing on RHEL6 is a bit messy. Eventually I used Python 3.4 from Rehat Collections reposoity, because it was the best version to support virtualenv which met Borgs requirements. Also I could not make fuse work because the available versions of fuse for RHEL6 are all <2.9, thus python module llfuse would not install. In the future I might work sround this using Docker since I am stuck with RHEL6 for a while.

To use borg, first one switches to the Python 3 enviroment, then to the borg env, per the setup docs. This scripts tend to have something like this near the beginning.

```
. /opt/rh/rh-python34/enable
. /root/borg-env/bin/activate
```
