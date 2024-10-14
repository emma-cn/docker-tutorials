# 使用 Ubuntu 24.04 作为基础镜像
FROM ubuntu:24.04

# 安装 Python3、pip 和虚拟环境工具
RUN apt-get update && apt-get install -y \
    python3 python3-pip python3-venv

# 设置容器内的工作目录
WORKDIR /app

# 将项目代码复制到容器中
COPY . .

# 创建虚拟环境
RUN python3 -m venv /app/venv

# 在虚拟环境中安装 FastAPI 和 Uvicorn
RUN /app/venv/bin/pip install fastapi uvicorn

# 暴露 FastAPI 的端口
EXPOSE 8000

# 使用虚拟环境中的 Uvicorn 启动应用程序
CMD ["/app/venv/bin/uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000", "--reload"]
