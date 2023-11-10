FROM python:2.7

# Install Java
RUN apt update && \
    apt install -y sudo && \
    sudo apt install default-jdk -y

## Pip dependencies
# Upgrade pip
RUN pip install --upgrade pip
# Install production dependencies
COPY ../bin/requirements.txt /tmp/requirements.txt
RUN pip install -r /tmp/requirements.txt && \
    rm /tmp/requirements.txt
# Install development dependencies

COPY ../. /tmp

CMD ["sh", "-c", "jupyter notebook --no-browser --ip 0.0.0.0 --port 8888 --allow-root --notebook-dir=/tmp/"]
EXPOSE 8888