# **Stake Wars: Episode III.** Challenge 14

- Published on: 2022-08-17
- Submitted by: Everstake
- Rewards: 15 DNP

## Description

In this challenge, participants will learn how to create, run, and modify the auto-backup node script. 

For this challenge, we recommend using Bash, however, Python can be used as well. 

## Acceptance criteria

- Create a script for the auto-backup of your node
- Make a backup on your reserve node
- Modify the auto-backup script

## Challenge submission

For submission, please fill out the [form](https://forms.gle/1MS9Jvhvq9YWbbwk7)  

Also, make sure to share a link to your GitHub repo with the script in the **Proof of Completion: URL** section. 

If you don't want to share it publicly, please share a script in the **Proof of Completion: Text** or upload a file in the **Proof of Completion: Files** section.

## Steps

### Part 1

**Auto-backup node**

A backup node is a separate server for taking and storing database snapshots.  
This is necessary, for example, to quickly transfer an up-to-date database to another server so that the new node is synchronized as quickly as possible, or to restore a damaged database

⚠️ Be aware that it takes time to copy the database. Do not use an auto-backup script on the validator node!

Example `backup.sh`

```bash
#!/bin/bash

DATE=$(date +%Y-%m-%d-%H-%M)
DATADIR=<WORK_DIR>
BACKUPDIR=<WORK_DIR>/backups/near_${DATE}

mkdir $BACKUPDIR

sudo systemctl stop near-main.service

wait

echo "NEAR node was stopped" | ts

if [ -d "$BACKUPDIR" ]; then
    echo "Backup started" | ts

    cp -rf $DATADIR/mainnet/data/ ${BACKUPDIR}/

    # Submit backup completion status, you can use healthchecks.io, betteruptime.com or other services
    # Example
    # curl -fsS -m 10 --retry 5 -o /dev/null https://hc-ping.com/xXXXxXXx-XxXx-XXXX-XXXx-...

    echo "Backup completed" | ts
else
    echo $BACKUPDIR is not created. Check your permissions.
    exit 0
fi

sudo systemctl start near-main.service

echo "NEAR node was started" | ts

```

- **For an automatic start:**

```bash
sudo nano /etc/crontab
```

Add line:

```bash
# Example of job definition:
# .---------------- minute (0 - 59)
# |  .------------- hour (0 - 23)
# |  |  .---------- day of month (1 - 31)
# |  |  |  .------- month (1 - 12) OR jan,feb,mar,apr ...
# |  |  |  |  .---- day of week (0 - 6) (Sunday=0 or 7) OR sun,mon,tue,wed,thu,fri,sat
# |  |  |  |  |
# *  *  *  *  * user-name command to be executed
0  12 *  *  * near      <WORK_DIR>/NEARmain/backup.sh >> <WORK_DIR>/NEARmain/backups/backup.log 2>&1
```

💡 This setting will automatically start database backup every day at 12:00


### Part 2

Try to make a backup on your backup node, and modify the auto-backup script :

- Save the data folder as an archive
- Check the folder with backups and remove the oldest 
- Write a simple script for quick database restoring 

## Update Log

Updated 2022-08-17: Creation
