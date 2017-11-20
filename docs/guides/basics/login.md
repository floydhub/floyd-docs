### Quick Preparation Checklist

- You must have a [FloydHub account](https://www.floydhub.com/signup)
- You must be [logged in to your web dashboard](https://www.floydhub.com/login)
- You must have `floyd-cli` [installed on your computer](install.md)

You can use the [floyd login](../../commands/login.md) command to log in to
your FloydHub account through your command line

### Logging In Using Username and Password

`floyd login` has a `--username` (or `-u`) flag and a `--password` (or `-p`)
flag that are used for logging in with the username and password. You can pass
both at the same time, or if you pass only the `-u` (or `--username`) flag with
your username, you'll be prompted for you password:

```
$ floyd login -u mckay
Please enter your password:
Login Successful as mckay
```

### Logging in Using an Auth Token

If you don't pass the `-u` (or `--username`) flag to `floyd login`, you will be
logging in using an auth token.

Here's an example of the standard workflow:

```bash
$ floyd login
Authentication token page will now open in your browser. Continue? [Y/n]: y
Please copy and paste the authentication token.
This is an invisible field. Paste token and press ENTER:
```

This will open your browser and display your authentication token. You can also
access this directly at
[floydhub.com/settings/security](https://www.floydhub.com/settings/security).
(*Note:* only visible if you are [logged in](https://www.floydhub.com/login) to
your web dashboard).

![Windows 10 Login](../../img/login_token.jpg)

Copy the token and paste it in your terminal.

### Logging in with an Auth Token Without Opening a Browser

Sometimes you may need to log in to Floyd on a computer that can't open a
browser. Using your
[token from floydhub.com](https://www.floydhub.com/settings/security), you can
log in without opening a browser by passing the `--token` flag to
`floyd login`:

```
$ floyd login --token
Please copy and paste the authentication token.
This is an invisible field. Paste token and press ENTER:
Login Successful
```

### Having problems with logging in using floyd-cli?

- Are you on a Windows machine? Please see our [FAQs for Windows](../../faqs/authentication.md#windows)
- Other problems? Check out our [Login FAQs](../../faqs/authentication.md#login) or [contact us](mailto:support@floydhub.com)
