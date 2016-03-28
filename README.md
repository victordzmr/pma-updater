# phpMyAdmin updater
Bash script that performs a secure update of an existing phpMyAdmin installation to the latest version.

## Features
* Detects if the existing installation is already up-to-date.
* It can be easily used with *cron*.

## License
This software is distributed under the MIT license. Please read LICENSE for information on the software availability and distribution.

## Installation
This bash script requires execution permissions and *jq*, a command-line JSON processor.

### OS X
Using [Homebrew](http://brew.sh):

```
chmod u+x pma-updater
brew install jq
```

### CentOS and RHEL
```
chmod u+x pma-updater
yum install jq
```

### Other operating systems
Visit the official [JQ website](https://stedolan.github.io/jq/) to get more information.

## Usage
```
sh pma-updater [, directory_name]
```

* `directory_name` is the relative or absolute path to the directory in which phpMyAdmin is installed. Default: `./phpmyadmin`.

## Cron
Using this script with *cron* is as easy as adding the following line to *crontab*, that will make the script check for updates every day at 6 AM.

```
0 6 * * * sh /path/to/the/script >/dev/null 2>&1
```

Visit [Crontab Generator](http://crontab-generator.org/) to automatically generate *crontab* lines.

## Example
```
sh pma-updater /home/victor/phpmyadmin
```

In this case, the script will update an existing phpMyAdmin installation in the directory `/home/victor/phpmyadmin` to the latest version if it is out-of-date.