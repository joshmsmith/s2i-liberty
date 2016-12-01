# s2i-liberty
Sample S2I Builder Image for Websphere Liberty on Openshift

# s2i-liberty-base
Base Docker image starting from `websphere-liberty`, adds Oracle JDK and Maven

Intermediate image created here because re-installing JDK and Maven over and over during S2I script testing was slow

# s2i-liberty
Source to Image builder for Liberty on Openshift. Includes basic S2I script for Maven build
