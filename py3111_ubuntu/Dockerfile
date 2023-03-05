FROM ubuntu:22.04

# update
RUN apt-get -y update && apt-get install -y \
sudo \
wget \
vim \
tree \
build-essential libbz2-dev libdb-dev \
libreadline-dev libffi-dev libgdbm-dev liblzma-dev \
libncursesw5-dev libsqlite3-dev libssl-dev \
zlib1g-dev uuid-dev 

WORKDIR /opt
RUN wget https://www.python.org/ftp/python/3.11.1/Python-3.11.1.tar.xz &&\
tar xJf Python-3.11.1.tar.xz && cd Python-3.11.1 && ./configure && make && sudo make install && rm -rf Python-3.11.1

# install datascience related packages
RUN python3 -m pip install --upgrade pip

# Install packages for data analysis
RUN python3 -m pip install numpy scipy pandas h5py matplotlib seaborn bokeh scikit-image tqdm jupyterlab

# Set working directory
WORKDIR /home
RUN mkdir work && cd work

WORKDIR / 

# CMD ["jupyter", "lab", "--ip=0.0.0", "--allow-root", "LabApp.token=''"]
