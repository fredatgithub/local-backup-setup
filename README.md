# Setting up local backups

## Actions

* [ ] Change .backup/launchd.plist to have your machine name
* [ ] Add backups.local to your /etc/hosts
* [ ] Add your ssh key to backups.local authorized_keys
* [ ] Update .backup/excludes

Then run:

    brew install terminal-notifier
    sudo mkdir -p /var/log/backup
    sudo chmod 0777 /var/log/backup
    ln -s ~/.backup/launchd.plist ~/Library/LaunchAgents/com.jagregory.backups.plist    
    launchctl load ~/Library/LaunchAgents/com.jagregory.backups.plist
    launchctl start com.jagregory.backups
