Login to Floyd.

### Usage
```bash
floyd login
```

### Description
You need to login to Floyd before running any other command. The login flow will require an access token from the Floydhub 
website. You will be prompted to enter you credentials to get your access token. Copy and paste the token on the command line 
to complete login.

### Example
```bash
$ floyd login
Access token page will now open in your browser. Continue? [Y/n]:
Please paste the code here:
Login Successful
```

### Authentication Tokens

Floyd uses [Json Web Tokens](https://jwt.io/introduction/) for authentication. Your 
token will be stored in the `~/.floydconfig` file. They are valid for 7 days after 
which you need to login again. This file will be removed when you [logout](/commands/logout).
