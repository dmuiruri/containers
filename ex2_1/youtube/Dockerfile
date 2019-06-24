FROM ubuntu:16.04 

ENV LC_ALL=C.UTF-8  

RUN apt-get update && apt-get install -y \ 
    curl python && \ 
    curl -L https://yt-dl.org/downloads/latest/youtube-dl -o /usr/local/bin/youtube-dl && \ 
    chmod a+x /usr/local/bin/youtube-dl 

WORKDIR /videos

ENTRYPOINT ["/usr/local/bin/youtube-dl"] 
