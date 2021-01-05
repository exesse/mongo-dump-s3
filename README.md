# mongo-dump
[![release Actions Status](https://github.com/exesse/mongo-dump-s3/workflows/release/badge.svg)](https://github.com/exesse/mongo-dump-s3/actions)
[![build Actions Status](https://github.com/exesse/mongo-dump-s3/workflows/build/badge.svg)](https://github.com/exesse/mongo-dump-s3/actions)
[![Codacy Badge](https://app.codacy.com/project/badge/Grade/0484d1d38b5d41318f0980126a1c45a9)](https://www.codacy.com/gh/exesse/mongodump-s3/dashboard?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=exesse/mongodump-s3&amp;utm_campaign=Badge_Grade)
[![DeepSource](https://deepsource.io/gh/exesse/mongodump-s3.svg/?label=active+issues&show_trend=true)](https://deepsource.io/gh/exesse/mongodump-s3/?ref=repository-badge)

 
Backup utility for MongoDB. Compatible with Azure, Amazon Web Services and Google Cloud Platform.

## Usage

Make sure that original MongoDB Database Tools are installed. Please follow instruction on [the official page](https://www.mongodb.com/try/download/database-tools) for platform specific installation.
Also make sure that `mongodump` command is in your path.

### Local
!Write installer
```bash
sudo apt update
sudo apt install python3 python3-pip mongo-tools
git clone git@github.com:exesse/mongo-dump.git && cd mongo-dump
python3 -m pip install -r requirments.txt
python3 main.py
```

### Docker
````bash
sudo docker run --name mongodb -d -p 27017:27017 mongo:2.6.12

sudo docker run --name mongo-dump --env-file dev.env -v /tmp/mongo-dump:/tmp/mongo-dump -v ~/dev.json:/mongo-dump/key.json:ro mongo-dump:0.0.1-dev
````

!Temporary 
```bash
sudo docker build -t mongo-dump:0.0.1-dev .

sudo docker stop mongo-dump && sudo docker rm mongo-dump && sudo docker rmi mongo-dump:0.0.1-dev
```