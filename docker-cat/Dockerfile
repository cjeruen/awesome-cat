FROM openjdk:8-jdk

ADD src/apache-maven-3.5.2.tar.gz /cat
ADD src/cat-2.0.0.tar.gz /cat
ADD src/mvn-repo.tar.gz /cat

COPY settings.xml /root/.m2/settings.xml
COPY data /data

ENV M2_HOME /usr/local/maven
ENV PATH $M2_HOME/bin:$PATH

RUN ln -s /cat/apache-maven-3.5.2 /usr/local/maven \ 
    && cp -R /cat/mvn-repo/* ~/.m2/repository/ \
    && cd /cat/cat-2.0.0 \
    && mvn clean install -DskipTests \
    && rm -rf /cat/mvn-repo

# timezone
RUN echo "Asia/Shanghai" > /etc/timezone

EXPOSE 2280
EXPOSE 2281

WORKDIR /cat/cat-2.0.0/cat-home

ENTRYPOINT ["mvn", "jetty:run"]
