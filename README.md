# 基于docker 的confluence 安装 和破解
## 1. 下载docker-compose.yaml文件
```
wget https://raw.githubusercontent.com/joker8023/confluence/master/docker-compose.yaml
```
## 2. 启动docker-compose
```
sudo docker-compose up -d
```
## 3. 破解confluence
 
 [破解文件](http://pan.baidu.com/s/1jIv9aZW ) 密码：91av
 破解文件和中文包都在里面
 如果失效请发邮件到18817814702@163.com提醒
 
### 3.1 复制并备份文件
复制原始文件
```
docker cp confluence:/opt/atlassian/confluence/confluence/WEB-INF/lib/atlassian-extras-decoder-v2-3.2.jar /home/gench/
```
进入容器 并备份文件

    docker exec -it confluence /bin/sh
    mv /opt/atlassian/confluence/confluence/WEB-INF/lib/atlassian-extras-decoder-v2-3.2.jar  /opt/atlassian/confluence/confluence/WEB-INF/lib/atlassian-extras-decoder-v2-3.2.jar.bak




### 3.2 使用破解工具生成新的jar文件
#### 3.2.1 confluence5.1-crack文件夹内
删除atlassian-extras-2.4.jar，
#### 3.2.2 使用3.1 3.2.2 copy文件的atlassian-extras-decoder-v2-3.2.jar 改成atlassian-extras-2.4.jar
#### 3.2.3 进入 iNViSiBLE ./keygen.sh 将记录下来的Service ID 输入，name可以随意填写
#### 3.2.4 点击patch选择刚改名的文件点击.gen！生成key，即生成

### 3.3 将atlassian-extras-2.4.jar改回atlassian-extras-decoder-v2-3.2.jar并复制回原先目录

```
docker cp /home/gench/atlassian-extras-decoder-v2-3.2.jar confluence:/opt/atlassian/confluence/confluence/WEB-INF/lib/
```
### 3.4 重启

```
docker stop confluence
docker start confluence
```

