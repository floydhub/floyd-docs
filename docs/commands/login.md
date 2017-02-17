Login to Floyd.

### Usage
```bash
floyd login
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| `--token`       |  False  | If specified, browser will not open. You can paste your token in the command line.|

### Description
You need to login to Floyd before running any other command. The login flow will require an access token from the Floydhub 
website. You will be prompted to enter you credentials to get your access token. Copy and paste the token on the command line 
to complete login.

In case you use remote machines and do not have access to the browser, you can copy the token from the 
[dashboard](https://www.floydhub.com/welcome) and use the `--token` parameter when you login.

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
