# Osa 1

1.1

```bash
docker ps -a
CONTAINER ID        IMAGE                               COMMAND                  CREATED             STATUS                      PORTS               NAMES
6dba12893a50        nginx                               "nginx -g 'daemon of…"   2 minutes ago       Exited (0) 33 seconds ago                       focused_sinoussi
83c1b069cea6        nginx                               "nginx -g 'daemon of…"   2 minutes ago       Exited (0) 17 seconds ago                       jovial_nash
85039edfbefb        nginx                               "nginx -g 'daemon of…"   2 minutes ago       Up 2 minutes                80/tcp              sleepy_bartik
```

1.2

```bash
docker container prune
WARNING! This will remove all stopped containers.
Are you sure you want to continue? [y/N] y
Deleted Containers:
6dba12893a500d6d291e0601945f2f1177164c08b927d7235ce5b6d46a4c9598
83c1b069cea6b363ccb222a66f5098fdc69dc2ce6fb1509dbfa320d384076a5d
847b8a627cb618e3acb0288cbf0e07c1bafc1662dbb0f49270339c8e88970427
071375b24406ed3cd336a657f7f4ce2284dd80e89abf94c6a3f3f2512aec77f5
b4cc8a9273663cc7d8efd8a15bb48109e95263b9a88a3e1e85a3735ed3126877
a080415518210387a858db51c2a46e9a73566524b81f95922a3db4c43601c33d
61500281f51e4e4f85d05acfe74793e98cfaa1febd59751b4f5d04e4ba679d0d
3351bc029783ea79c6d154dd6c48eeeb41b7e42552a51a4946b91afd693222d7
e646ed7fd7a1cea95b76997b92be33fda0bfb2309d687212001ba165f03d9712
418d086719f18d52cacf280e9764811642477a7b98014a775986c395860eed7c

Total reclaimed space: 41.74MB
MacBook-Pro-Yekku:docker-course yekku$ docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS               NAMES
85039edfbefb        nginx               "nginx -g 'daemon of…"   5 minutes ago       Up 5 minutes        80/tcp              sleepy_bartik

MacBook-Pro-Yekku:docker-course yekku$ docker image prune
WARNING! This will remove all dangling images.
Are you sure you want to continue? [y/N] y
Total reclaimed space: 0B
MacBook-Pro-Yekku:docker-course yekku$ docker images
REPOSITORY                          TAG                 IMAGE ID            CREATED             SIZE
nginx                               latest              f949e7d76d63        45 hours ago        126MB
fav_distro                          xenial              657d80a6401d        7 days ago          121MB
ubuntu                              16.04               657d80a6401d        7 days ago          121MB
ubuntu                              xenial              657d80a6401d        7 days ago          121MB
ubuntu                              latest              2ca708c1c9cc        7 days ago          64.2MB
devopsdockeruh/pull_exercise        latest              d9854bc0e13a        6 months ago        75.3MB
devopsdockeruh/exec_bash_exercise   latest              489b6d8f2ab8        7 months ago        897MB
MacBook-Pro-Yekku:docker-course yekku$
```

1.3

```bash
docker run -it devopsdockeruh/pull_exercise
Give me the password: basics
You found the correct password. Secret message is:
"This is the secret message"
```

1.4

```bash
docker run -d devopsdockeruh/exec_bash_exercise
docker exec -it hopeful_greider bash
tail -f ./logs.txt
Wed, 25 Sep 2019 19:54:30 GMT
Wed, 25 Sep 2019 19:54:33 GMT
Secret message is:
"Docker is easy"
```

1.5

```bash
docker run -it --name web ubuntu:16.04
root@847b8a627cb6:/# apt-get update
root@847b8a627cb6:/# apt-get -qq -y install curl
root@847b8a627cb6:/# echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website;
Input website:
helsinki.fi
Searching..
<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">
<html><head>
<title>301 Moved Permanently</title>
</head><body>
<h1>Moved Permanently</h1>
<p>The document has moved <a href="http://www.helsinki.fi/">here</a>.</p>
</body></html>
root@847b8a627cb6:/#
```

1.6

Dockerfile-1.6

```bash
-h,             --help                  to show this message
-a [age],       --adult [age]           to check if you're older than 18
-c [time],      --clock [time]          to start a clock
-t [size],      --triangle [size]       to draw a triangle, takes second argument as the size
```

1.7

Dockerfile-1.7

```bash
Successfully tagged curler:latest
MacBook-Pro-Yekku:osa-1 yekku$ docker run -it curler
Input website:
helsinki.fi
Searching..
<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">
<html><head>
<title>301 Moved Permanently</title>
</head><body>
<h1>Moved Permanently</h1>
<p>The document has moved <a href="http://www.helsinki.fi/">here</a>.</p>
</body></html>
```

1.8

```bash
docker build -t second-one .
docker run -v $(pwd)/logs.txt:/usr/app/logs.txt second-one
(node:1) ExperimentalWarning: The fs.promises API is experimental
Wrote to file /usr/app/logs.txt
Wrote to file /usr/app/logs.txt
Wrote to file /usr/app/logs.txt
Wrote to file /usr/app/logs.txt
Wrote to file /usr/app/logs.txt
Wrote to file /usr/app/logs.txt
Wrote to file /usr/app/logs.txt
Wrote to file /usr/app/logs.txt
Wrote to file /usr/app/logs.txt
Wrote to file /usr/app/logs.txt
Wrote to file /usr/app/logs.txt

Secret message is:
"Volume bind mount is easy"
Thu, 03 Oct 2019 20:03:59 GMT
```

```bash

```
