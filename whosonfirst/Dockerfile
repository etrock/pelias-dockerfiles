# base image
FROM pelias/libpostal_baseimage

# downloader apt dependencies
# note: this is done in one command in order to keep down the size of intermediate containers
RUN apt-get update && apt-get install -y bzip2 unzip && rm -rf /var/lib/apt/lists/*

# clone repo
RUN git clone https://github.com/venicegeo/pelias-whosonfirst.git /code/pelias/whosonfirst

# change working dir
WORKDIR /code/pelias/whosonfirst

# install npm dependencies
RUN npm install

# run tests
RUN npm test
