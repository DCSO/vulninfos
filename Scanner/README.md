# Using Loki for the file based detection of web services with Apache Struts Vulnerabilities
## What's Loki?
Loki is a Scanner for Simple Indicators of Compromise. It provides a detection
for filenames, hashs, yara or C2 Back Connect.

Special thanks to Florian Roth - https://github.com/Neo23x0
## Setup Loki
Loki can be obtained here: https://github.com/Neo23x0/Loki

Follow the instructions from the Readme.md to setup Loki on Linux or Windows
based systems. After Loki Setup is complete, copy your desired scan file
like `Wordpress/vuln-wordpress-plugins-hash` to `./Loki/signature-base/iocs/.`

Loki is now ready to scan the file system for vulnerable files.

## Start Scan
**Be aware, that a file scan may disturb or interrupt running service's. Make a
Backup or Snapshot of your system before you start a scan!**

For a faster and less disturbing scan, we recommend limiting the search range as
far as possible e.g to the appropriate application folder.

On Linux
```
$> python loki.py --intense -p /path/to/the/server/webapps
```

On Windows
```
loki.exe --intense -p C:\path\to\the\server\webapps
```

If you still want to scan the whole system

On Linux
```
$> python loki.py --intense
```

On Windows
```
loki.exe --intense
```

The output of a scan might look like this:
![Loki Output](example.jpg)

For additional Information's read the Loki documentation at
https://github.com/Neo23x0/Loki/blob/master/README.md

## Vulnerability Files
All indicator files can be obtained from the corresponding subfolder.
Please read the appropriate README.md for further information about subject and
usage.
