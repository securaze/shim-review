FROM ubuntu:20.04
LABEL maintainer="richie@securaze.com"
LABEL version="1.0"
LABEL description="This is the Docker Image to build shim 15.4 for Securaze"
ARG DEBIAN_FRONTEND=noninteractive
RUN apt update
RUN apt install -y --no-install-recommends build-essential devscripts git wget
RUN git clone https://github.com/richiesecuraze/shim/ --branch 15.4.sec1 --recursive
WORKDIR /shim
RUN wget https://raw.githubusercontent.com/securaze/shim-review/master/certificate/codesign_ev_2021.cer
RUN make VENDOR_CERT_FILE=codesign_ev_2021.cer
RUN sha256sum shimx64.efi
