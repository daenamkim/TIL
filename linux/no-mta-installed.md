# No MTA installed

When monitored `syslog` in Ubuntu 18.04 LTS I got an error from CRON as below.

```sh
Jul 10 05:50:01 oootoko-base CRON[4732]: (CRON) info (No MTA installed, discarding output)
```

It's because there is no MTA(Mail Transfer Agent) to send a mail. So just do as below. :)

```sh
$ sudo apt-get install postfix
```

After running a CRON you will receive a mail `/var/mail` then you will find out what happended.

[Source](https://askubuntu.com/questions/222512/cron-info-no-mta-installed-discarding-output-error-in-the-syslog)
