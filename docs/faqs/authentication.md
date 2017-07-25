## Signup

### How does the free CPU / GPU hours work?

Every one who signups to Floydhub will receive 2 hours of free CPU / GPU time
for running your projects. We hope this will give you enough time to evaluate
Floydhub for your needs. We are working on a new free plan right now to better
help new users explore the platform.


## Login

### Windows

### I get "Invalid Token" error on my Windows 10 machine when I run floyd login.

If you are using Windows command shell, there is an issue with pasting the token using the 
standard `Ctrl + V` shortcut. You need to use the Shell's Edit menu to paste the token. After copying the token from the browser, right click on the top bar of the command shell and select Edit -> Paste. See image below:

![Windows 10 Login](../img/login_win_10.jpg)

### I still get the "Invalid Token" error after trying the above suggestion.

In some windows shells (like Git Bash) there is an extra space added to the token field
before you paste the token. So you need to hit Backspace and clear out the field before pasting 
the token. So the steps are:

1. Type `floyd login` in the console.
2. From the FloydHub web page, select the token and click on the "Copy to clipboard" button.
![Windows 10 Login](../img/login_token.jpg)
3. In the console, hit "backspace" a few times to remove the extra characters from the token login prompt request.
4. Right click on the menu bar, and select "Edit", and then "Paste"
5. Then press "Enter"

You should be able to login successfully now. If it's still not working, please give it a try on powershell.



{!contributing.md!}
