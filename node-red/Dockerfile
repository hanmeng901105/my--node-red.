ARG BUILD_FROM=ghcr.io/hassio-addons/base:17.2.1
# hadolint ignore=DL3006
FROM $BUILD_FROM

# 安装系统级依赖
RUN apk add --no-cache python3 py3-pip

# 创建Python虚拟环境
RUN python3 -m venv /usr/src/python_env
ENV PATH="/usr/src/python_env/bin:$PATH"

# 安装Python库
COPY requirements.txt /tmp/
RUN pip install --no-cache-dir -r /tmp/requirements.txt && \
    rm -rf /tmp/*