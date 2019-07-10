# Docker

# 目次
- [ゴール](#goal)
- [Dockerイメージの取得](#DockerImage)
- [Dockerからコンテナを作成](#DockerContainer)
- [Dockerコンテナとイメージを削除を削除](#delete)

<a id="goal"></a>
## ゴール
Dockerを用いてコンテナのイメージをつかむ。  
![container](https://github.com/eiji-noguchi/Docker/blob/images/containerImage.png)
こちらも[参考](https://www.slideshare.net/KoheiTokunaga/ss-122754942)

※Dockerがインストールされていること。     
[公式サイト](https://docs.docker.com/get-started/)を参照

<a id="DockerImage"></a>
## Dockerイメージの取得
[Dockerhub](https://hub.docker.com/_/hello-world/?tab=description)からimageを取得する。
```
>docker pull hello-world
latest: Pulling from library/hello-world
Digest: sha256:41a65640635299bab090f783209c1e3a3f11934cf7756b09cb2f1e02147c6ed8
Status: Image is up to date for hello-world:latest
```
取得したimageを確認する。
```
>>docker image ls
REPOSITORY                  TAG                 IMAGE ID            CREATED             SIZE
hello-world                 latest              fce289e99eb9        6 months ago        1.84kB
```
これでDockerhubからimageを取得できた。

<a id="DockerContainer"></a>
## Dockerからコンテナを作成
取得したimageからコンテナを作成し、hello-worldを表示させる。
```
>docker run hello-world

Hello from Docker!
This message shows that your installation appears to be working correctly.
:
```
コンテナの一覧を表示し、コンテナが作られていることを確認する。
```
>docker container ls --all
CONTAINER ID        IMAGE                       COMMAND                  CREATED              STATUS                          PORTS                                NAMES
fc6a81078967        hello-world                 "/hello"                 About a minute ago   Exited (0) About a minute ago                                        naughty_cocks
```


<a id="delete"></a>
## Dockerコンテナとイメージを削除を削除
作成したコンテナを削除
```
>docker rm fc6a81078967
```
取得したimageを削除
```
>docker rmi hello-world
```