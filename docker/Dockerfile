#####################
#
#####################
FROM nvidia/cuda:12.3.1-base-ubuntu20.04 as base-deps

# Install Python and pip using apt-get
RUN apt-get update && \
    apt-get install -y python3.9 && \
    apt-get install -y python3-pip && \
    apt-get install -y git && \
    apt-get clean


# Set python3.9 as the default python version
RUN update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.9 1

## Set the Python environment variables
#ENV PATH="/usr/bin/python3:${PATH}"
#ENV PYTHON_PIP_VERSION=21.3.1

FROM base-deps as final-stage

WORKDIR /app

COPY requirements.txt .

#RUN pip3 install --upgrade pip3 setuptools

RUN pip3 install -r requirements.txt

COPY ../. .

