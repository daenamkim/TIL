# Slack Notification

## Slack

- Move to [Slack App Directory](https://slack.com/apps) after login.
- Install Jenkins CI.

---

## Jenkins

- Move to Manage Jenkins > Manage Plugins > Available tab.
- Install [Slack Notification Plugin](https://wiki.jenkins.io/display/JENKINS/Slack+Plugin).
- Move to Manage Jenkins > Configure System.
- Fill out `Base URL`, `Integration Token` in Global Slack Notifier Settings.
- In your proejct in Jeknins > Configure > Add post-build action in Post-build Actions > Slack Notifications.
