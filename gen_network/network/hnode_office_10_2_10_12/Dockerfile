# 基础镜像
FROM xinzp/tiaozhanbei:v1.2
RUN sed -i 's/archive.ubuntu.com/mirrors.aliyun.com/g' /etc/apt/sources.list
RUN sed -i 's/security.ubuntu.com/mirrors.aliyun.com/g' /etc/apt/sources.list 
RUN apt-get install -y iproute2 iptables

# 暴露端口
EXPOSE 80 81 873

# 复制启动脚本到容器内的 /usr/local/bin 目录
COPY startup.sh /usr/local/bin/start_services.sh

# 确保启动脚本具有执行权限
RUN chmod +x /usr/local/bin/start_services.sh

# 入口点设置为启动所有服务的脚本
ENTRYPOINT ["/usr/local/bin/start_services.sh"]