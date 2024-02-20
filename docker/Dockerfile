#####################
#
#####################
FROM nvidia/cuda:12.3.1-base-ubuntu20.04 as base-deps

# Install Python and pip using apt-get
RUN apt-get update && \
    apt-get install -y python3 && \
    apt-get install -y python3-pip && \
    apt-get clean

# Set the Python environment variables
ENV PATH="/usr/bin/python3:${PATH}"
ENV PYTHON_PIP_VERSION=21.3.1

FROM base-deps as final-stage

WORKDIR /app

COPY requirements.txt .

RUN pip install -r requirements.txt

COPY ../. .

