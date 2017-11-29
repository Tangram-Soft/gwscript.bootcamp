# Welcome to GatewayScript Bootcamp!

##### Let's get started
In order to start gatewayscripting, you need to get a few things installed first.
While you might not be familiar with these tools, don't worry - this is a one timer and we will escort you though the process of installing everything to get you started.

##### What do we need?
1) git client - We uploaded everything to GitHub, using git you'll be able to pull everything to your workstation.
2) docker - Your very own DataPower instance will run on top of docker.

_______
__Only for Windows 7/8 (and not later):__
DockerToolbox provides us a virtual machine that runs docker on top of it.
Download DockerToolbox from here: https://download.docker.com/win/stable/DockerToolbox.exe

Install Docker Toolbox following the installation wizard.
__Make sure you choose full installation (Including git cmd).__

###### Let's get our docker environment ready.
Open cmd  
Execute the following command:  
```
docker-machine create --virtualbox-cpu-count "3" --virtualbox-memory "4096" boot2docker
docker pull ibmcom/datapower:7.5.2.8.289749
```
_______

We created a special IDE so it'll be a lot more fun to develop with :)
```
git clone https://github.com/Tangram-Soft/dpanda.ide.git
```

once git is done, run the following in PowerShell:
```
cd dpanda.ide
docker create -it -v $PWD/config:/drouter/config -v $PWD/local:/drouter/local -p 9090:9090 -p 9080:9080 -p 22:22 -p 8000-8010:8000-8010 -p 5550:5550 -p 5554:5554 -e DATAPOWER_ACCEPT_LICENSE=true -e DATAPOWER_INTERACTIVE=true --name idg.dpanda ibmcom/datapower:7.5.2.8.289749
docker start idg.dpanda
```

Then run the following from DataPower's CLI:
```
switch dpanda;co;crypto;keygen CN dpanda-gui rsa 2048 gen-sscert;exit;exit;switch default
user dpanda;access-level privileged;password dpanda;suppress-password-change;exit
```

After logging in, enable GUI via Configure Crypto Certificate and Configure Crypto Key. These pages can be reached by searching crypto in the navigation bar. In each menu's dpanda-gui	entry, set Administrative state to 'disabled', then re-select 'enabled' and Apply.

Now we can begin!
Go to https://[docker-machine ip]/dpanda/webIDE.html
Default localhost is 127.0.0.1, and port is set to 9080.
