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
