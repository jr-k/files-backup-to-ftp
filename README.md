# fbtf
Simple file backup dump rotate system

# help
Usage: `fbtf [-options]`<br />
where options include:
-	`-r | --rotate`		rotate counter (e.g: -r=10, default: 10)
-	`-c | --crondir`		cron directory, useful to store dump in different cron (e.g: -c=hourly, default: default)
-	`-i | --input`		input directory, location where dumps are initially stored (e.g: -i=/home/mybucket)
-	`-o | --output`		output directory, location where dumps will be stored (e.g: -o=/home/filesbackups)
-	`-u | --ftpuser`		ftp username
-	`-w | --ftppwd`		ftp password
-	`-s | --ftphost`		ftp host
-	`-p | --ftpport`		ftp port
-	`-h | --help`		shows this help

Crontab entries
- `* * * * * /usr/local/sbin/fbtf -r=60 -c="minutely1"`
- `*/5 * * * * /usr/local/sbin/fbtf -r=12 -c="minutely5"`
- `0 * * * * /usr/local/sbin/fbtf -r=24 -c="hourly"`
- `0 1 * * * /usr/local/sbin/fbtf -r=30 -c="daily"`
- `0 0 * * 0 /usr/local/sbin/fbtf -r=52 -c="weekly"`
- `0 0 1 * * /usr/local/sbin/fbtf -r=12 -c="monthly"`
