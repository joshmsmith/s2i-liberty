# s2i-liberty-base
FROM websphere-liberty:webProfile7

MAINTAINER heywoodbanks

ENV MAVEN_VERSION=3.3.9 \
    LICENSE=true

# update, install oracle JDK
RUN apt-get update && \
    apt-get install curl software-properties-common python-software-properties -y --no-install-recommends && \
    add-apt-repository ppa:webupd8team/java && \
    apt-get update && \
    echo debconf shared/accepted-oracle-license-v1-1 select true | debconf-set-selections && \
    echo debconf shared/accepted-oracle-license-v1-1 seen true | debconf-set-selections && \
    apt-get install oracle-java8-set-default -y

# install maven
RUN (curl -v https://www.apache.org/dist/maven/maven-3/$MAVEN_VERSION/binaries/apache-maven-$MAVEN_VERSION-bin.tar.gz | \
    tar -zx -C /usr/local) && \
    ln -sf /usr/local/apache-maven-$MAVEN_VERSION/bin/mvn /usr/local/bin/mvn && \
    mkdir -p $HOME/.m2
