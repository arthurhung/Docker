# Docker
#### Docker 指令

指令                 | 功能
-------------------- |------------------------
service docker start | 起 docker server


指令                 | 功能
-------------------- |------------------------
docker images        | 目前擁有的images
docker run -it [ImageID] /bin/bash | run images
docker commit [container name] hello-world:v1.0 | 打包image
docker rmi [ImageID] | 刪除 images


指令                 | 功能
-------------------- |------------------------
docker exec -it [containerID] bash | 進入 container
docker ps            | 目前正在 run 的 container
sudo docker stop [containerID] | 停止 container 
docker rm [containerID] | 刪除 container


#### Docker file

python 3 範例
用 requirements.txt 安裝 python 套件



```
FROM python:3 
ENV PYTHONUNBUFFERED 1
RUN mkdir /code
WORKDIR /code
ADD requirements.txt /code/
RUN pip install -r requirements.txt
ADD . /code/
```
