# backup-mysql
Shell Script to Backup MySQL Databases on Webserver Daily 
This Script Performs a full backup of the MySQL Databases on a Server. 
Be sure to edit the configuration options at the beginning of the script to match your environment prior to executing.
The end result will be a TAR archive of each website with the name '(current-datestamp)-$db.sql'. 
For Backing up your Website Files please see our backup-www script.

# Usage:

1. Pull up a terminal or SSH into the target server.

2. Logon as root

<pre>sudo -i</pre>

3. Download the installer script.

<pre>wget https://raw.githubusercontent.com/YlanNaly/automate-mysqldump-script/main/backup-mysql.sh</pre>

4. Edit the configuration options at the beginning of the script to match your environment prior to executing.
<pre>
----------------------------------------
 OPTIONS
----------------------------------------
USER='mysql-username'       # MySQL User
PASSWORD='mysql-password' # MySQL Password
DAYS_TO_KEEP=5    # 0 to keep forever
GZIP=0            # 1 = Compress
BACKUP_PATH='/home/backup/mysql'
----------------------------------------
</pre>

5. Make the script executable

<pre>chmod +x backup-mysql.sh</pre>

6. Run the script.

<pre>./backup-mysql.sh</pre>

8. Setup a cronjob to run the script daily/weekly if you choose.
<pre>
5 1   * * * /etc/backup-mysql.sh >/dev/null 2>&1
</pre>
