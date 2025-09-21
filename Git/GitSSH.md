# Git with SSH Authentication

An `SSH key` is an access credential in the [SSH protocol](https://www.ssh.com/academy/ssh/protocol). Its function is similar to that of user names and passwords, but the keys are primarily used for automated processes and for implementing single sign-on by system administrators and power users. [_refference_](https://www.ssh.com/academy/ssh-keys)

## Check for existing SSH key

Open `Git Bash` and enter the following command:

```bash
ls -al ~/.ssh
# Lists the files in your .ssh directory, if they exist
```

Check the directory listing to see if you already have a public SSH key. By default, the filenames of supported public keys for GitHub are one of the following.

* id_rsa.pub

* id_ecdsa.pub

* id_ed25519.pub

## Generating a new SSH key

Open `Git Bash` and enter the following command:

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

_Note:_ If you are using a legacy system that doesn't support the Ed25519 algorithm, use:

```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

## Adding a new SSH key

```bash
clip < ~/.ssh/id_ed25519.pub
# Copies the contents of the id_ed25519.pub file to your clipboard
```

---

## Additional

Go to `Setting` on Github then click on `SSH and GPG keys`. Click on `New SSH key`, Enter Title then paste the content that you've copied from `id_ed25519.pub` into `Key` Section.

Thanks

_refference:_ [GitHub Docs](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)