FROM ubuntu:18.04

# Upgrade to python 3.9
ENV TZ=America/Edmonton
ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update && apt-get install -y software-properties-common
RUN add-apt-repository ppa:deadsnakes/ppa
RUN apt-get update && apt-get install -y build-essential \
    python3.9 python3.9-dev \
    python3-pip python3.9-distutils 

# Symlink python3 -> python
RUN ln -s /usr/bin/python3.9 /usr/bin/python

# Python requirements
ADD ./dockerfiles/requirements.txt /
RUN pip3 install -r /requirements.txt

# Python requirements
ADD ./dockerfiles/requirements.txt /
RUN pip3 install -r /requirements.txt

# Init working dir
RUN mkdir /bot

# ENV VARS
ENV WORKING_DIR=/bot
ENV PYTHONPATH=/bot

# keep alive
CMD ["tail", "-f", "/dev/null"]
