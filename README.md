# Postfix Checks

This repository contains usual Postfix regular expressions for [`body_checks`](http://www.postfix.org/header_checks.5.html) and [`header_checks`](http://www.postfix.org/header_checks.5.html).    

Scope of the project is to use [Postfix Built-in Content Inspection](http://www.postfix.com/BUILTIN_FILTER_README.html) to limit SPAM and phishing on MTA Level.    

### Instalation

Edit your `/etc/postfix/main.cf`:

```
# Content Inspection
header_checks = regexp:/etc/postfix/header_checks
body_checks = regexp:/etc/postfix/body_checks
```

You should setup the `cron.daily` job for automatic updates:

```
sudo wget -O /etc/cron.daily/postfix-checks https://raw.githubusercontent.com/sorinpohontu/Postfix-Checks/master/etc/cron.daily/postfix-checks

sudo chown root:root /etc/cron.daily/postfix-checks
sudo chmod +x /etc/cron.daily/postfix-checks

```
