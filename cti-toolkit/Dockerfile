# A basic cti-toolkit client
# To use:
#    - docker build -t "certau/ctitoolkit:dockerfile" .
#    - modify the conf/ctitoolkit.conf file by uncommenting the output format and adding your username and password
#    - place edited configuration file, certificates and private key in conf directory
#    - call docker container as follows: 
#      docker run -it -v /path/to/conf:/etc/cti-toolkit certau/ctitoolkit:dockerfile

FROM ubuntu:latest
MAINTAINER CERT Australia <info@cert.gov.au>
RUN apt-get update && apt-get install -y \
    git \
    python-certifi \
    python-pip \
    python-dev \
    libxml2-dev \
    libxslt1-dev \
    libz-dev && \
    apt-get clean 
RUN pip install cti-toolkit==1.1.0.dev3
RUN git clone https://github.com/CIRCL/PyMISP.git &&\
   cd PyMISP &&\
   python setup.py install

CMD ["stixtransclient.py", "-c", "/etc/cti-toolkit/ctitoolkit.conf"]
