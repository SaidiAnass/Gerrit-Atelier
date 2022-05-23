# Gerrit Code Review: Atelier GL

## Table des matières

- [Installation](#installation-et-configuration)
- [Workshop](#atelier)

## Installation et configuration

Before installing gerrit make sure you have

- [Git for windows](https://gitforwindows.org/) ou bien [Git for MacOs](https://git-scm.com/download/mac)
- [JDK](https://www.oracle.com/java/technologies/downloads/#jdk17-windows)

Intallation de Gerrit localement:

- [Windows](https://github.com/Sl0v3C/Install_Gerrit_4Windows_Guide)
- [Linux](https://gerrit-documentation.storage.googleapis.com/Documentation/3.5.0.1/linux-quickstart.html)

Pour notre cas on va travailler avec un outil dans le cloud:

- [GerritHub](http://gerrithub.io/)

Click Signin and follow the steps

<p>
    <img src="./imgs/gerrit%20signup.png">
</p>
<p>
    <img src="./imgs/gerrit-login.png">
</p>

<p>
    <img src="./imgs/gerrit-github.png">
</p>

<p>
    <img src="./imgs/authorization.png">
</p>

<p>
    <img src="./imgs/login-gerrit-github.png">
</p>

<p>
    <img src="./imgs/import-github-repos.png">
</p>

<p>
    <img src="./imgs/voila.png">
</p>

### SSH Keys for GerritHub

When working with a GerittHub repository, you'll often need to identify yourself to GerritHub using your username and password. An SSH key is an alternate way to identify yourself that doesn't require you to enter you username and password every time.

SSH keys come in pairs, a public key that gets shared with services like GerritHub, and a private key that is stored only on your computer. If the keys match, you're granted access.

- Generating an SSH key pair

```sh
$ sshkey-gen -t rsa -C "gerrituser@example.com"
> Generating public/private rsa key pair.
> Enter file in which to save the key (/Users/username/.ssh/id_rsa):
> Enter passphrase (empty for no passphrase):
> Enter same passphrase again:
```

- Add your public key to GerritHub

```sh
$ cat ~/.ssh/id_rsa.pub
```

The output should look something like this:

```
ssh-rsa AAAAB3NzaC1yc2EAAAABIwAAAQEA879BJGYlPTLIuc9/R5MYiN4yc/YiCLcdBpSdzgK9Dt0Bkfe3rSz5cPm4wmehdE7GkVFXrBJ2YHqPLuM1yx1AUxIebpwlIl9f/aUHOts9eVnVh4NztPy0iSU/Sv0b2ODQQvcy2vYcujlorscl8JjAgfWsO3W4iGEe6QwBpVomcME8IU35v5VbylM9ORQa6wvZMVrPECBvwItTY8cPWH3MGZiK/74eHbSLKA4PY3gM4GHI450Nie16yggEg2aTQfWA1rry9JYWEoHS9pJ1dnLqZU3k/8OWgqJrilwSoC5rGjgp93iu0H8T6+mEHGRQe84Nk1y5lESSWIbn6P636Bl3uQ== your@email.com
```

Copy the contents of the output to your clipboard.

- Go to **Settings**
<p>
    <img src="./imgs/gerrit-settings.png">
</p>

- Select **SSH-Keys** from the side menu
<p>
    <img src="./imgs/ssh-keys-gerrit.png">
</p>

- Paste the contents of your clipboard into the Key text box.
<p>
    <img src="./imgs/paste-ssh-key.png">
</p>

## Workshop

- Connect to gerrit

```console
$ ssh auth
```

- Test connection `ssh -p 29418 <username>@<gerritHostName>`
- Visit this link
- Clone repository on local machine
- Create a local branch
- Make changes
- Commit changes
- Push changes HEAD:refs/for/<branch>
- Switch to Gerrit UI
- Review change (File section)
- Add reviewers to review my code
- Submit code review
- Merge to the main branch
