## Login using floyd-cli

### Quick Preparation Checklist

- You must have a [FloydHub account](https://www.floydhub.com/login)
- You must be [logged in to your web dashboard](https://www.floydhub.com/login)
- You must have `floyd-cli` [installed on your computer](../guides/install.md)

You can use the [floyd login](../commands/login.md) command to login to your FloydHub account through your command line

```bash
$ floyd login
Authentication token page will now open in your browser. Continue? [Y/n]: y
Please copy and paste the token from the welcome page.
This is an invisible field. Paste token and press ENTER:
```

This will open your browser and display your authentication token. You can also access this directly at [floydhub.com/settings/security](https://www.floydhub.com/settings/security). (*Note:* only visible if you are [logged in](https://www.floydhub.com/login) to your web dashboard). 
![Windows 10 Login](../img/login_token.jpg)
Copy the token and paste it in your terminal.

### Having problems with logging in using floyd-cli?

- If you cannot open your browser from the terminal (e.g. you are SSH-ing into a remote server), use the `--token` flag. See [floyd login](../commands/login.md) for more details
- Are you on a Windows machine? Please see our [FAQs for Windows](../faqs/authentication.md#windows)
- Other problems? Check out our [Login FAQs](../faqs/authentication.md#login) or [contact us](mailto:support@floydhub.com)