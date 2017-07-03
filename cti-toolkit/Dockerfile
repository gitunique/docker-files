# A basic cti-toolkit client
# To use:
#    - docker build -t "certau_ctitoolkit:dockerfile" .
#    - modify the cti-toolkit.conf file by uncommenting the output format and adding your username and password
#    - place edited configuration file, certificate and private key in conf director
#    - call docker container as follows: docker run -it -v /path/to/conf:/etc/cti-toolkit

FROM ubuntu:latest
MAINTAINER CERT Australia <info@cert.gov.au>
RUN apt-get update && apt-get install -y python-pip python-dev libxml2-dev libxslt1-dev libz-dev && apt-get clean 
RUN pip install cti-toolkit==1.1.0.dev1
CMD ["stixtransclient.py", "-c", "/etc/cti-toolkit/ctitoolkit.conf"]
