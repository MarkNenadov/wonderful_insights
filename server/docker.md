Docker insights
===============

Installing Docker
---------------------------------------------------------------------------------
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository        "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
       $(lsb_release -cs) \
       stable"
sudo apt-get update
apt-get -y install docker-ce
```

Verify Docker is Installed Correctly
-------------------------

```docker run hello-world```

Stopping and Removing the Docker Instance
-----------------------------------------

```
docker stop $(docker ps -a -q)
docker rm $(docker ps -a -q)
```
