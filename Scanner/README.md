# Using Loki for file-based detection of web services with Apache Struts Vulnerabilities

## What's Loki?

Loki is a scanner for simple Indicators of Compromise, detecting them via
filenames, hashes, YARA rules or C2 back connect.

Special thanks to Florian Roth (https://github.com/Neo23x0 or
[@cyb3rops](https://twitter.com/cyb3rops) on Twitter).

## Setup Loki

Loki can be obtained here: https://github.com/Neo23x0/Loki

Follow the instructions given in Loki's [README.md](https://github.com/Neo23x0/Loki/blob/master/README.md)
to set up Loki on Linux or Windows based systems. After the Loki setup is
complete, copy the `struts-sha1-hash.txt` or `struts-core-sha1-hash.txt` to
`./Loki/signature-base/iocs/`.

Loki is now ready to scan the file system for vulnerable Struts JARs.

## Start Scan
**Be aware that a file scan may disturb or interrupt running services. It is recommended to have a
backup or snapshot of your system available before starting a scan!**

For a faster and less disruptive scan, we recommend to only scan the
application server-specific directories:

On Linux
```
$> python loki.py --intense -p /path/to/the/server/webapps
```

On Windows
```
loki.exe --intense -p C:\path\to\the\server\webapps
```

If you still want to scan the whole system:

On Linux
```
$> python loki.py --intense
```

On Windows
```
loki.exe --intense
```

An example scan output might look like this:

![Loki Output](example.jpg)

For additional information please refer to the upstream Loki documentation
at https://github.com/Neo23x0/Loki/blob/master/README.md.

## Vulnerability indicator files

All indicator files can be obtained from the corresponding subfolder.
Please read the appropriate README.md for further information about subject and
usage.
