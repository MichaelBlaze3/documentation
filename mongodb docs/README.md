# MongoDB 

## Content
* [Installation on macOS](#Installation-on-macos)
* [Run Mongo Service](#Run-mongo-service)

### Installation on macOS
Perform the following steps to install the mongodb database on macOS.

#### Download Mongodb
Go to the MongoDB website https://www.mongodb.com and download the Community Server.
In this perticular documentation we will download the `.tgz`.

Now that mongodb.tgz is downloaded, we will procede to unpack the mongodb folder from `.tgz`.

We will get something like this: 
```
mongodb-osx-x86_64-3.6.2
```

Now, we will need to move this folder into the following path: `/usr/local`

In order to get into the previuos path, type the following commands in the terminal
```
cd /
cd usr
cd local
```

Now we are in the local folder, just to confirm, type in terminal the following command
```
pwd
```
We should get something like this:
```
/usr/local
```

Create a directory called mongodb and copy and paste the content of `mongodb-osx-x86_64-3.6.2` into this folder.

With the terminal, position your self inside the mongodb folder.
```
Current location: /usr/local

cd mongodb

Now your current location is /usr/local/mongodb
```

Now, lets create a new  folder with the following command
```
sudo mkdir -p data/db
```
Lets get the value of current user  by typing this command:
```
whoami
```

Now type the following command `chown`.
```
sudo chown whoami_value /data/db 
```
Now type `cd`, this will take you to the root of the terminal

Now lets type the following command
```
ls -la
```
This will display a list of files including the file `.bash_profile`.
Lets open this file by typing the following command.
```
open .bash_profile
```

This will show the content of the file. Now in this file, we will enter the instructions to make the mongodb command available on any location in the system.


```
export MONGO_PTH=/usr/local/mongodb
export PATH=$PATH:$MONGO_PTH/bin
``` 

Save the file.

Now enter the command
```
source .bash_profile
```
Restart the terminal.

### Run Mongo Service
Now, for testing..
Lets open 2 terminal windows
On the first terminal window, type mongod. This will start the mongodb service.

On the second window, type mongo and hit enter. You will be able to see the interaction between the two terminal windows(server and client).


