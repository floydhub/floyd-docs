Login to Floyd.

### Usage
```bash
floyd login
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| `--token`       |  False  | If specified, browser will not open. You can paste your token in the command line. <br>**Note**: This is only supported with `version 0.7.2+` of `floyd-cli`. If you get an error, please upgrade using `pip install -U floyd-cli` and try again|
| `--username`    |  False  | FloydHub username. If specified, must include `--password` |
| `--password`    |  False  | FloydHub password |

### Description
You need to login to Floyd before running any other command. The login flow will require an access token from the Floydhub 
website. You will be prompted to enter you credentials to get your access token. Copy and paste the token on the command line 
to complete login.

Alternatively, you can use the username and password parameters to directly login from the command line. In case you
run in to any issues logging in with username / password, try logging in with the token as explain above.

### Example
To automatically open your browser
```bash
$ floyd login
Authentication token page will now open in your browser. Continue? [Y/n]:
Please paste the token here:
Login Successful as alice
```

In case you use remote machines and do not have access to the browser, you can copy the token from the 
[dashboard](https://www.floydhub.com/welcome) and use the `--token` parameter when you login.
```bash
$ floyd login --token
Please copy and paste the token here:
Login Successful as alice
```

If you are using the credentials directly:
```bash
$ floyd login --username alice --password <redacted>
Login Successful as alice
```

### Authentication Tokens

Floyd uses [Json Web Tokens](https://jwt.io/introduction/) for authentication. Your 
token will be stored in the `~/.floydconfig` file. They are valid for 7 days after 
which you need to login again. This file will be removed when you [logout](/commands/logout).

{!contributing.md!}
