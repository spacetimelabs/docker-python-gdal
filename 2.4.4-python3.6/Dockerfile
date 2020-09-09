# Uses Ubuntu Bionic
FROM ubuntu:18.04

# Update and install gdal dependencies
RUN apt-get update && \
    apt-get -y install \
        wget \
        software-properties-common \
        postgresql-client libpq-dev \
        git python-pip make build-essential libssl-dev \
        zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev \
        python3-pip locales \
        python3-dev \
        python3-numpy

# Install Gdal
# See: https://mothergeo-py.readthedocs.io/en/latest/development/how-to/gdal-ubuntu-pkg.html
RUN add-apt-repository "ppa:ubuntugis/ppa"

RUN apt-get update && apt-get install -y libgdal-dev

ENV CPLUS_INCLUDE_PATH=/usr/include/gdal
ENV C_INCLUDE_PATH=/usr/include/gdal

# Use GDAL >= 2.2.1 and < 3.0
# If you need GDAL 3, check this https://github.com/thinkWhere/GDAL-Docker out
ENV GDAL_VERSION=2.4.4

# Install some Gdal version using pip
# RUN pip install GDAL==${GDAL_VERSION}

# Set python aliases for python3
RUN echo 'alias python=python3' >> ~/.bashrc
RUN echo 'alias pip=pip3' >> ~/.bashrc
RUN echo 'alias ll="ls -lha --color=auto"' >> ~/.bashrc

CMD ["python"]

