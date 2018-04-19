Login to Floyd.

### Usage
```bash
floyd login
```

### Options
| Name, shorthand | Default | Description |
| --------------- | ------- | ----------- |
| `--username`    |  False  | FloydHub username. If specified, must include `--password` |
| `--password`    |  False  | FloydHub password |
| `--token`       |  False  | If specified, authentication token will be used instead of credentials |

### Description
You need to login to FloydHub before running any other command. You can use your FloydHub username and password to 
login. Alternatively you can also use the access token available in the 
[Auth Token](https://www.floydhub.com/settings/security) page on the website to login.

### Example

```bash
$ floyd login
Login with your FloydHub username and password to run jobs.
Username [alice]: alice
Password: 
Login Successful as alice
```

For automated systems use the authentication token.
```bash
$ floyd login --token
Please paste the authentication token from https://www.floydhub.com/settings/security.
This is an invisible field. Paste token and press ENTER:
Login Successful as alice
```

You can also specify the credentials on the command line.
```bash
$ floyd login --username alice --password <redacted>
Login Successful as alice
```

### Authentication Tokens

Floyd uses [Json Web Tokens](https://jwt.io/introduction/) for authentication. Your 
token will be stored in the `~/.floydconfig` file. They are valid for 7 days after 
which you need to login again. This file will be removed when you [logout](/commands/logout).

{!contributing.md!}
