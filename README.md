### Serverless Single Page Apps

[Ben Randy's "Serverless Single Page Apps"](https://pragprog.com/book/brapps/serverless-single-page-apps)
#### Clone the repository

```unix
mkdir -p ~/GitHub/rkiel
cd ~/GitHub/rkiel
git clone https://github.com/rkiel/learnjs.git
cd learnjs
```

#### Make it your own

```unix
rm -rf .git
git init
git add .
git commit -m "Initial commit"
```

#### AWS Console

Create a new user

* click **IAM**
* click **Users**
* click **Create New Users**
* enter `serverless-spa`

Generate credentials

* check **Generate an access key for each user**
* click **Create**
* click **Download Credentials**

Grant user permissions

* click **IAM**
* click **Users**
* click **serverless-spa**
* click **Permissions**
* click **Attach Policy**
* type in `power`
* check **PowerUserAccess**
* click **Attach Policy**

#### Prepare AWS credentials before starting up Vagrant

```unix
grep serverless-spa ~/Downloads/credentials.csv |awk  -F "\"*,\"*" '{print $2}' > aws_access_key_id.txt
grep serverless-spa ~/Downloads/credentials.csv |awk  -F "\"*,\"*" '{print $3}' > aws_secret_access_key.txt
rm -f ~/Downloads/credentials.csv
```

#### Start Vagrant

```unix
vagrant up
```

#### Start the web server

```unix
cd /vagrant
./sspa server
````

#### Browser

[http://192.168.33.60:9292](http://192.168.33.60:9292)

#### AWS CLI

```unix
aws configure --profile admin
```

#### Create and Deploy bucktet

```unix
./sspa create_bucket yyz-serverless-spa
./sspa deploy_bucket yyz-serverless-spa
```

#### Browser

[http://yyz-serverless-spa.s3-website-us-east-1.amazonaws.com](http://yyz-serverless-spa.s3-website-us-east-1.amazonaws.com)
