#borgbackup

[Borgbackup](https://borgbackup.readthedocs.io) is a deduplicating backup system. After install this script 
will make backups for you. Run as root.

## Useage

Set up Python 3 virtual local environment to be used and invoked by root, and which will be in turn used to install and run the borg-backup script. This is a way to ensure the Python environment consistently meets requirements, so you could approach this step in different ways if you wanted to. The [borgbackup install docs](http://borgbackup.readthedocs.io/en/stable/installation.html) provide the necessary steps for different operating systems.

Modify .borg.env and paths in script to meet your needs. Copy .borg.env to /root. Copy the script to /etc/cron.daily and ensure executable. 

Use the commented commands to initialize your repositories, test and use!
