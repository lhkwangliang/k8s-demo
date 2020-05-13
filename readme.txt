# 构建镜像
docker build -t myapp:1.0 .

# 启动容器
docker run --name myapp --net=host -d myapp:1.0

# k8s
kubectl apply -f myapp.yaml


# 导出镜像
docker save -o openjdk_8-jdk-alpine.tar.gz openjdk:8-jdk-alpine

# 导入镜像
docker load -i openjdk_8-jdk-alpine.tar.gz


# 拆分文件
tar czf - openjdk_8-jdk-alpine.tar.gz | split -b 20m - openjdk_8-jdk-alpine.tar.gz_

# 合并文件
cat openjdk_8-jdk-alpine.tar.gz_* >openjdk_8-jdk-alpine.tar.gz
