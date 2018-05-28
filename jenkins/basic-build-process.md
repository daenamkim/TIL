# Basic Build Process

## GitHub

### GitHub Settings

- Repository > Settings > Integration & services > Add service > Jenkins (GitHub plugin) > In Jenkins hook url, input `[Jenkins HOST]/github-webhook/`.

---

## Jenkins Server

### SSH Settings

- [Add SSH Settings](https://github.com/daenamkim/til/blob/master/jenkins/ssh-connection.md)

### Install Jenkins Plugins

- Move to Manage Jenkins > Manage Plugins.
- Install [SSH](https://plugins.jenkins.io/ssh).
- Install [Publish Over SSH](https://plugins.jenkins.io/publish-over-ssh).
- Install [GitHub](https://wiki.jenkins.io/display/JENKINS/Github+Plugin).
- Install [GitHub PUll Request](https://plugins.jenkins.io/ghprb).
- Install [Slack Notification](https://github.com/daenamkim/til/blob/master/jenkins/slack-notification.md) if you want.

### Add a Server Settings

- Move to Manage Jenkins > Configure System.
- Add a server with hostname (recommended to add a list /etc/hosts.) at **Publish over SSH**.
- Add GitHub Auth at **GitHub Pull Request Builder**.
- Notice that credentials were up to your way to setup.

### Create a New Job

- New Item > Enter an item name > Freestyle Project > OK
- Inoput `Project name` in General tab.
- Select `GitHub project` > Add a repository's web URL in General tab.
- Select `Git` and fill `Repository URL` in Source Code Management tab.
- Select `GitHub hook trigger for GITScm polling` in Build Triggers tab.
- `Add build step` in Build tab > Excute shell > Fill anything you want to build.
- `Add post-build action` in Post-build Actions tab > Send build artifacts over SSH if you need.
- `Add post-build action` in Post-build Actions tab > Slack Notifications if you need.
