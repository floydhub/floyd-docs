### Quick Preparation Checklist

- You must have a [FloydHub account](https://www.floydhub.com/signup)
- You must be [logged in to your web dashboard](https://www.floydhub.com/login)
- You must have `floyd-cli` [installed on your computer](install.md)

You can use the [floyd login](../../commands/login.md) command to log in to
your FloydHub account through your command line

### Logging In Using Username and Password

Use the `floyd login` command to login to FloydHub from the cli.

```bash
$ floyd login
Login with your FloydHub username and password to run jobs.
Username [alice]: alice
Password: 
Login Successful as alice
```

### Logging in Using an Auth Token

Alternatively, you can also use the access token available in the [Auth Token](https://www.floydhub.com/settings/security) 
page on the website to login.

```bash
$ floyd login --token
Please paste the authentication token from https://www.floydhub.com/settings/security.
This is an invisible field. Paste token and press ENTER:
Login Successful as alice
```

### Having problems with logging in using floyd-cli?

- Are you on a Windows machine? Please see our [FAQs for Windows](../../faqs/authentication.md#windows)
- Other problems? Check out our [Login FAQs](../../faqs/authentication.md#login) or [contact us](mailto:support@floydhub.com)
