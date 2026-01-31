# 使用官方MySQL镜像
FROM mysql:8.0

# 设置环境变量
ENV MYSQL_ROOT_PASSWORD=Xjie@1234.
ENV MYSQL_DATABASE=sampledb
ENV MYSQL_USER=xiaojie
ENV MYSQL_PASSWORD=Xjie@1234.

# 复制自定义配置文件
COPY my.cnf /etc/mysql/conf.d/

# 创建数据目录（如果需要持久化）
RUN mkdir -p /var/lib/mysql

# 暴露MySQL端口
EXPOSE 3306

# 设置健康检查
HEALTHCHECK --interval=30s --timeout=10s --start-period=60s --retries=3 \
  CMD mysqladmin ping -h localhost -u root -p${MYSQL_ROOT_PASSWORD} || exit 1