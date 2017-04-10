FROM centos:6.8

RUN yum install -y wget; yum upgrade -y; yum update -y;  yum clean all

# Set correct environment variables.
ENV	LANG en_US.UTF-8
ENV	LC_ALL en_US.UTF-8

ENV JDK_VERSION 8u121
ENV JDK_BUILD_VERSION b13
RUN wget --no-cookies --no-check-certificate --header "Cookie: gpw_e24=http%3A%2F%2Fwww.oracle.com%2F; oraclelicense=accept-securebackup-cookie" "http://download.oracle.com/otn-pub/java/jdk/$JDK_VERSION-$JDK_BUILD_VERSION/e9e7ea248e2c4826b92b3f075a80e441/jdk-$JDK_VERSION-linux-x64.rpm" && rpm -i jdk-$JDK_VERSION-linux-x64.rpm; rm -f jdk-$JDK_VERSION-linux-x64.rpm; yum clean all
ENV JAVA_HOME /usr/java/default

RUN yum remove curl;  yum clean all
ENTRYPOINT ["java"]