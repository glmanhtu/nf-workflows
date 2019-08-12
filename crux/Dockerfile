################## BASE IMAGE ######################

FROM openjdk:8-jre-slim

RUN  apt-get update \
  && apt-get install -y wget unzip \
  && rm -rf /var/lib/apt/lists/*

################## METADATA ######################
LABEL base_image="biocontainers:v1.0.0_cv4"
LABEL version="3"
LABEL software="crux"
LABEL software.version="2.1"
LABEL about.summary="a software toolkit for tandem mass spectrometry analysis"
LABEL about.home="http://cruxtoolkit.sourceforge.net/"
LABEL about.documentation="http://cruxtoolkit.sourceforge.net/"
LABEL about.license_file="http://cruxtoolkit.sourceforge.net/"
LABEL about.license="SPDX:Apache-2.0"
LABEL extra.identifiers.biotools="crux"
LABEL about.tags="Proteomics"

################## MAINTAINER ######################
MAINTAINER Felipe da Veiga Leprevost <felipe@leprevost.com.br>

################## INSTALLATION ######################

RUN ZIP=crux-2.1.Linux.x86_64.zip && \
  wget https://github.com/BioDocker/software-archive/releases/download/Crux/$ZIP -O /tmp/$ZIP && \
  unzip /tmp/$ZIP -d /usr/local/crux/ && \
  rm /tmp/$ZIP && \
  ln -sv /usr/local/crux/*/bin/* /usr/local/bin/

WORKDIR /data/