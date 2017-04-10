FROM centos:6.8

RUN yum install -y wget; yum install -y unzip; yum upgrade -y; yum update -y;  yum clean all

# Set correct environment variables.
ENV	LANG en_US.UTF-8
ENV	LC_ALL en_US.UTF-8

ENV JDK_VERSION_MAJOR 8
ENV JDK_VERSION_MINOR 121
ENV JDK_BUILD_VERSION 13
ENV JAVA_HOME /usr/java/default

# Download and install JDK
RUN wget --no-cookies --no-check-certificate --header "Cookie: gpw_e24=http%3A%2F%2Fwww.oracle.com%2F; oraclelicense=accept-securebackup-cookie" "http://download.oracle.com/otn-pub/java/jdk/${JDK_VERSION_MAJOR}u${JDK_VERSION_MINOR}-b${JDK_BUILD_VERSION}/e9e7ea248e2c4826b92b3f075a80e441/jdk-${JDK_VERSION_MAJOR}u${JDK_VERSION_MINOR}-linux-x64.rpm" && rpm -i jdk-${JDK_VERSION_MAJOR}u${JDK_VERSION_MINOR}-linux-x64.rpm; rm -f jdk-${JDK_VERSION_MAJOR}u${JDK_VERSION_MINOR}-linux-x64.rpm; yum clean all

# Download and install Java Cryptography Extension (JCE) Unlimited Strength
RUN wget --no-cookies --no-check-certificate --header "Cookie: gpw_e24=http%3A%2F%2Fwww.oracle.com%2F; oraclelicense=accept-securebackup-cookie" "http://download.oracle.com/otn-pub/java/jce/${JDK_VERSION_MAJOR}/jce_policy-${JDK_VERSION_MAJOR}.zip" && unzip /jce_policy-${JDK_VERSION_MAJOR}.zip && cp -v /UnlimitedJCEPolicyJDK8/*.jar ${JAVA_HOME}/jre/lib/security && rm -f jce_policy-8.zip && rm -rf UnlimitedJCEPolicyJDK8/;

RUN yum remove curl; yum clean all
ENTRYPOINT ["java"]