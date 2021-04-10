###### MongoDB Installation on Ubuntu 18.04-16.04 Command
### Step-1: At First Update & Upgrade
`sudo apt-get update && sudo apt-get upgrade`


### Step-2: – Setup Apt Repository
###### Import GPK key for the MongoDB apt repository on your system using the following command. This is required to test packages before installation:
`sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 656408E390CFB1F5`

###### Let’s add MongoDB APT repository url in /etc/apt/sources.list.d/mongodb.list.
#### For Ubuntu 18.04 LTS:
`echo "deb [ arch=amd64 ] https://repo.mongodb.org/apt/ubuntu bionic/mongodb-org/4.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb.list`

#### For Ubuntu 16.04 LTS:
`echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/4.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb.list`
