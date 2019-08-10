### Docker启动容器命令

1. 进入Docker容器命令

   ```shell
   docker exec -i -t myredis  /bin/bash
   ```

2. 启动redis命令

   ```shell
   #使用默认配置文件
   sudo docker run --name myredis -v /home/lanxing/data/docker/redis/data:/data -p 6379:6379  -d redis redis-server --appendonly yes
   #使用自定义配置文件
   sudo docker run --name myredis -v /home/lanxing/data/docker/redis/data:/data -v /home/lanxing/data/docker/redis/conf/redis.conf:/usr/local/etc/redis/redis.conf  -p 6379:6379  -d redis:4.0.14 redis-server /usr/local/etc/redis/redis.conf  --appendonly yes
   ```

3. 删除镜像

   ```shell
   sudo docker rmi -f 3c41ce05add9
   ```

4. 删除容器

   ```shell
   sudo docker rm -f ca2754dbd784e522a9ce742c26604d08402563ef13a6ca46e5e2ab556a01470f
   ```

5. 重启容器

   ```shell
   sudo docker restart myredis
   ```

6. docker启动gitlab

   ```shell
   sudo docker run --detach \
   --hostname gitlab.example.com \
   --publish 443:443 --publish 80:80 --publish 22:22 \
   --name gitlab \
   --restart always \
   --volume /home/lanxing/data/docker/gitlab/config:/etc/gitlab \
   --volume /home/lanxing/data/docker/gitlab/logs:/var/log/gitlab \
   --volume /home/lanxing/data/docker/gitlab/data:/var/opt/gitlab \
   gitlab/gitlab-ce:latest
   ```

7. 

