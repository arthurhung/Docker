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
RUN git clone http://stsuser:stsuser.130@128.110.22.99/sts/loan.git
RUN git clone http://stsuser:stsuser.130@128.110.22.99/sts/sinoTradeWebStatic.git
RUN git clone http://stsuser:stsuser.130@128.110.22.99/sts/sinoTradeWebRestAPI.git
RUN mv sinoTradeWebStatic static
RUN mv sinoTradeWebRestAPI rest
RUN cd /loan
WORKDIR /loan
RUN pip install -r requirements.txt

RUN mkdir /loan/logs

# VOLUME ["/etc/nginx"]
EXPOSE 80 443

```

docker build -t [fileName] .

#### Docker volumes

sudo docker run -it --name logs -d -v /ap/loan-logs:/loan/logs 7660c37b5abb
sudo docker run -it --name [comtainerName] -d -v /host/path:/docker/path [imagesID]


