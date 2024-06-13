Tags: #docker #ssh #forwarding #GUI

# Setup SSH X Forwarding in Docker
- __Description:__ Guide to setup SSH X forwarding in docker
- __Author:__ Kuan-Hsien Wu
- __Contact:__ jordan@c-link.com.tw
- __Date:__ 2024.04.08

## Setup X GUI programs in Docker

### In HOST machine
1. Allow local connection to docker
    ```
    xhost +local:docker
    ```
2. Share environment variable and sockets between docker and host when running `docker run`
    ```
    docker run ... -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix ...
    ```

### In Docker
1. You can use `xeyes` to test. If it works, it should pop-up a window with eyes staring at you
    ```
    apt update; apt -y install x11-apps; xeyes
    ```

## Setup SSH Server in Docker

### In Docker
1. Install SSH server
    ```
    apt update; apt -y install openssh-server
    ```
2. If you are using root to login in, you need to
    - Set `PermitRootLogin` in `/etc/ssh/sshd_config` to `yes`
        ```
        #/etc/ssh/sshd_config
        ...
        PermitRootLogin yes
        ...
        ```
    - Then restart the ssh service
        ```bash
        service ssh restart
        ```

### In HOST
1. Find container IP for SSH login
    ```
    sudo docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' <CONTAINER_ID>
    ```

## Setup SSH X Forwarding in Docker

### In Docker
1. For X forwarding, `.Xauthority` file is required to do authentication. You can generate one with following lines
    ```bash
    #Just for backup
    cp .Xauthority old.Xauthority # Just for backup

    #Generate .Xauthority file
    touch .Xauthority
    xauth generate :0 . trusted
    xauth add ${HOST}:0 . $(xxd -l 16 -p /dev/urandom)

    #Run xauth list, if it works, the output should be something like the following
    #154ea9cc7460/unix:0  MIT-MAGIC-COOKIE-1  5611863305fdda4d9c951cc5eab591e6
    xauth list
    ```

# Reference
- https://superuser.com/questions/806637/xauth-not-creating-xauthority-file
- http://blog.lujun9972.win/blog/2018/04/24/docker%E5%AE%B9%E5%99%A8%E4%B8%AD%E8%B7%91gui%E7%9A%84%E6%9C%80%E7%AE%80%E5%8D%95%E6%96%B9%E6%B3%95/index.html
