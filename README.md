###### MongoDB Installation on Ubuntu 18.04-16.04 Command
### Step-1: At First Update & Upgrade
`sudo apt-get update && sudo apt-get upgrade`


### Step-2: Setup Apt Repository
###### Import GPK key for the MongoDB apt repository on your system using the following command. This is required to test packages before installation:
`sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 656408E390CFB1F5`

###### Let’s add MongoDB APT repository url in /etc/apt/sources.list.d/mongodb.list.
#### For Ubuntu 18.04 LTS:
`echo "deb [ arch=amd64 ] https://repo.mongodb.org/apt/ubuntu bionic/mongodb-org/4.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb.list`

#### For Ubuntu 16.04 LTS:
`echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/4.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb.list`

###### After adding required APT repositories, use the following commands to install MongoDB on your systems. It will also install all dependent packages required for MongoDB:

### Step-3: Install MongoDB on Ubuntu
`sudo apt update`

#### Default Version:
`sudo apt install mongodb-org` OR

#### If you want to install any specific version of MongoDB, define the version number as below:
`sudo apt install mongodb-org=4.4.1 mongodb-org-server=4.4.1 mongodb-org-shell=4.4.1 mongodb-org-mongos=4.4.1 mongodb-org-tools=4.4.1`

### Step-4: Manage MongoDB Service

###### After installation, MongoDB will start automatically. 
#### Enable MongoDB Service:
`sudo systemctl enable mongod.service`
#### Start MongoDB Service:
`sudo systemctl start mongod.service`

#### Status check after start MongoDB Service:
`sudo systemctl status mongod.service`

###### Output:

`
sudo systemctl status mongod.service
● mongod.service - MongoDB Database Server
   Loaded: loaded (/lib/systemd/system/mongod.service; enabled; vendor preset: enabled)
   Active: active (running) since Thu 2021-04-08 07:48:49 UTC; 30s ago
     Docs: https://docs.mongodb.org/manual
 Main PID: 25924 (mongod)
   CGroup: /system.slice/mongod.service
           └─25924 /usr/bin/mongod --config /etc/mongod.conf
Apr 08 07:48:49 ip-172-31-18-128 systemd[1]: Started MongoDB Database Server.
`
#### Stop MongoDB Service:
`sudo systemctl stop mongod.service`

#### Restart MongoDB Service:
`sudo systemctl restart mongod.service`

### Step-5: Verify MongoDB Installed version

#### MongoDB Version Check:
`mongod --version`

###### Output:
`db version v4.4.1
Build Info: {
    "version": "4.4.1",
    "gitVersion": "ad91a93a5a31e175f5cbf8c69561e788bbc55ce1",
    "openSSLVersion": "OpenSSL 1.1.1  11 Sep 2018",
    "modules": [],
    "allocator": "tcmalloc",
    "environment": {
        "distmod": "ubuntu1804",
        "distarch": "x86_64",
        "target_arch": "x86_64"
    }
}
`
