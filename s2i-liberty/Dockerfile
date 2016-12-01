# s2i-liberty
FROM heywoodbanks/s2i-liberty-base

MAINTAINER heywoodbanks

ENV WEBSPHERE_LIBERTY_VERSION=1.0 \
    MAVEN_VERSION=3.3.9 

ENV LICENSE accept

LABEL io.k8s.description="Platform for WARs on WAS Liberty Profile" \
      io.k8s.display-name="s2i-liberty x.y.z" \
      io.openshift.expose-services="9080:http" \
      io.openshift.tags="builder,liberty,java,javaee"

# Defines the location of the S2I  
LABEL io.openshift.s2i.scripts-url=image:///usr/local/s2i
# Copy the S2I scripts from ./.s2i/bin/ to /usr/local/s2i when making the builder image
COPY ./.s2i/bin/ /usr/local/s2i

RUN mkdir -p /opt/s2i/destination
    
#------------------------------------------
RUN chown -R 1001:1001 /opt/ibm/wlp/
USER 1001
#------------------------------------------
