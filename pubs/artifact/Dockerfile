FROM rocker/verse:4.1.0

RUN apt-get update

RUN apt-get install -V -y \
  libudunits2-dev \
  libgdal-dev

COPY deps.R .

ENV SYSCONF_HOME /sysconf
ENV R Rscript
RUN Rscript deps.R

RUN git clone http://github.com/eitanf/sysconf
WORKDIR sysconf/
RUN git checkout peerj21-submitted
WORKDIR pubs/artifact
RUN make

CMD /bin/bash
