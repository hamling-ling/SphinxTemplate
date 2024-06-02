# How to setup
#
# Build docker image
# > docker build -f Dockerfile \
#   -t sphinx .

# pdf に変換できない版 (軽量)
#FROM sphinxdoc/sphinx:7.3.7
# latex で pdf に変換可能版 (重量級)
FROM sphinxdoc/sphinx-latexpdf:7.3.7

ENV PLANTUML_VERSION=1.2024.5
ENV PLANTUML_DIR=/usr/local/bin
ENV TERM=xterm-256color

RUN apt-get update && apt-get install -y software-properties-common

# これがないと JRE のインストールでこける
# https://stackoverflow.com/questions/58160597/docker-fails-with-sub-process-usr-bin-dpkg-returned-an-error-code-1
RUN mkdir -p /usr/share/man/man1

RUN apt-get update && apt-get install -y \
    ca-certificates \
    wget \
    curl \
    unzip \
    openjdk-17-jre \
    graphviz \
    fontconfig \
    fonts-dejavu \
    fonts-takao \
    fonts-ipafont \
    fonts-ipaexfont \
    texlive-font-utils \
    doxygen

RUN wget "https://github.com/plantuml/plantuml/releases/download/v${PLANTUML_VERSION}/plantuml-mit-${PLANTUML_VERSION}.jar" -O plantuml.jar
RUN mv plantuml.jar ${PLANTUML_DIR}

RUN python3 -m pip install --no-cache-dir \
    docutils sphinx-autobuild doc8 rstcheck \
    sphinx_rtd_theme sphinxcontrib-httpdomain \
    sphinxcontrib-plantuml \
    sphinxcontrib-bibtex \
    myst_parser \
    sphinxcontrib-mermaid

ENV PLANTUML_JAR_PATH ${PLANTUML_DIR}/plantuml.jar
