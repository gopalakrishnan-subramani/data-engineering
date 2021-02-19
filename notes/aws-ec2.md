
```
sudo apt update

sudo apt upgrade
```

https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2-linux.html

```
sudo apt install unzip
```

```
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
```

setting up a aws profile.. aaws cli, python, node.js....
https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html


```
cd ~

mkdir .aws

touch ~/.aws/credentials

touch ~/.aws/config
```

setup the credentials

```
nano ~/.aws/credentials
```

and paste below

```
[default]
aws_access_key_id=YOURKEY_HERE
aws_secret_access_key=YOUR_SECRET_KEY
```

default region

```
nano ~/.aws/config
```

```
[default]
region=us-east-2
```


```
aws s3 ls
```
