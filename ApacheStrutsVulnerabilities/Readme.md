# Using Loki for the file based detection of web services with Apache Struts Vulnerabilities
## What's Loki?
Loki is a Scanner for simple Indicators of Compromise. It provides a detection
for filenames, hashws, yara or C2 back connect.

Special thanks to Florian Roth - https://github.com/Neo23x0 - check him out on Twitter: https://twitter.com/cyb3rops
## Setup Loki
Loki can be obtained here: https://github.com/Neo23x0/Loki

Follow the instructions from the Readme.md to setup Loki on Linux or Windows
based systems. After the Loki Setup is complete, copy the `struts-sha1-hash.txt`
or `struts-core-sha1-hash.txt` to `./Loki/signature-base/iocs/.`

Loki is now ready to scan the file system for vulnerable Struts JAR's

## Start Scan
**Be aware, that a file scan may disturb or interrupt running service's. Make a
Backup or Snapshot of your system before you start a scan!**

For a faster and less disruptive scan, we recommend to only scan the directories
of the Application Server

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

## Struts Hash Files
**struts-core-sha1-hash.txt**

It contains only hashes from the Struts Core JAR files and should be used for
a quick scan of the application server or sytem

**struts-sha1-hash.txt**

It contains all hashes from the `struts-core-sha1-hash.txt` as whole as
additional Struts library JAR's that possible indicates to a vulnerable Apache
Strut Version.

### List of covered CVE's
* Apache Struts CVE-2017-9805 Remote Code Execution Vulnerability
* Apache Struts CVE-2017-9791 Remote Code Execution Vulnerability
* Apache Struts CVE-2017-5638 Remote Code Execution Vulnerability

### List of covered Struts versions
* Apache Struts 2.3.31
* Apache Struts 2.3.30
* Apache Struts 2.3.28
* Apache Struts 2.3.24
* Apache Struts 2.3.5
* Apache Struts 2.3.4 1
* Apache Struts 2.3.4
* Apache Struts 2.2.3
* Apache Struts 2.2.1 1
* Apache Struts 2.2
* Apache Struts 2.1.8
* Apache Struts 2.1.6
* Apache Struts 2.1.5
* Apache Struts 2.1.2
* Apache Struts 2.1.1
* Apache Struts 2.5.9
* Apache Struts 2.5.8
* Apache Struts 2.5.7
* Apache Struts 2.5.6
* Apache Struts 2.5.5
* Apache Struts 2.5.4
* Apache Struts 2.5.3
* Apache Struts 2.5.2
* Apache Struts 2.5.12
* Apache Struts 2.5.11
* Apache Struts 2.5.10
* Apache Struts 2.5.1
* Apache Struts 2.5
* Apache Struts 2.3.8
* Apache Struts 2.3.7
* Apache Struts 2.3.33
* Apache Struts 2.3.32
* Apache Struts 2.3.29
* Apache Struts 2.3.28.1
* Apache Struts 2.3.24.3
* Apache Struts 2.3.24.2
* Apache Struts 2.3.24.1
* Apache Struts 2.3.20.3
* Apache Struts 2.3.20.2
* Apache Struts 2.3.20.1
* Apache Struts 2.3.20
* Apache Struts 2.3.16.3
* Apache Struts 2.3.16.2
* Apache Struts 2.3.16.1
* Apache Struts 2.3.16
* Apache Struts 2.3.15.3
* Apache Struts 2.3.15.2
* Apache Struts 2.3.15.1
* Apache Struts 2.3.15
* Apache Struts 2.3.14.3
* Apache Struts 2.3.14.2
* Apache Struts 2.3.14.1
* Apache Struts 2.3.14
* Apache Struts 2.3.1.2
* Apache Struts 2.3.1.1
* Apache Struts 2.3.1
* Apache Struts 2.2.3.1
* Apache Struts 2.1.4
* Apache Struts 2.1.3

### List of additional Struts versions
Because of their slightly high age, the hash files also contains the following
Struts versions
* Apache Struts 1.2
* Apache Struts 1.2.2
* Apache Struts 1.2.4
* Apache Struts 1.2.6
* Apache Struts 1.2.7
* Apache Struts 1.2.8
* Apache Struts 1.2.9
* Apache Struts 1.3.5
* Apache Struts 1.3.8
* Apache Struts 1.3.9
* Apache Struts 1.3.10
