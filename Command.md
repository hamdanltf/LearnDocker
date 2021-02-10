###### **instal docker linux**

```sh
$ sudo apt-get update

$ sudo apt-get install apt-transport-https ca-certificates curl gnupg-agent software-properties-common

$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"

$ sudo apt-get update

$ sudo apt-get install docker-ce docker-ce-cli containerd.io
```

###### **Test Docker installation**

After completing the installation steps, test out Docker by running `sudo docker run hello-world`. This should download and run the test container printing *"hello world"* to your console.



###### **Install docker compose**

```sh
sudo curl -L "https://github.com/docker/compose/releases/download/1.28.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose
```

###### **Testing Docker Compose**

After completing, test your installation by running `docker-compose -v`. This should print the version and build numbers to your console.



###### **Add non-root user**

1. Create the `docker` group.

   ```shell
   $ sudo groupadd docker
   ```

2. Add your user to the `docker` group.

   ```shell
   $ sudo usermod -aG docker $USER
   ```

3. Log out and log back in so that your group membership is re-evaluated.

   If testing on a virtual machine, it may be necessary to restart the virtual machine for changes to take effect.

   On a desktop Linux environment such as X Windows, log out of your session completely and then log back in.

   On Linux, you can also run the following command to activate the changes to groups:

   ```shell
   $ newgrp docker 
   ```

4. Verify that you can run `docker` commands without `sudo`.

   ```
   $ docker run hello-world
   ```





###### **Auto start on boot**

To automatically start Docker and Containerd on boot for other distros, use the commands below:

```shell
$ sudo systemctl enable docker.service
$ sudo systemctl enable containerd.service
```

To disable this behavior, use `disable` instead.

```shell
$ sudo systemctl disable docker.service
$ sudo systemctl disable containerd.service
```





###### Check docker version

```shell
$ docker version
```

