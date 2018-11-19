FROM java:8-jdk as jdk8

MAINTAINER Kozin Vladyslav
LABEL Description="This image is used to show the Allure reposting"
LABEL Version="0.0.1"
ENV GRADLE_VERSION="4.10.2" MAIN_DIR="/allure-docker-example" MAIN_JAR="allure-docker-example-1.1.0.jar"

FROM jdk8 as depend
# Install dependencies
RUN apt-get install -fy unzip git

FROM depend As gradle
# Install Gradle
RUN wget https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip && \
   unzip gradle-${GRADLE_VERSION}-bin.zip && \
   mv gradle-${GRADLE_VERSION} /opt/ && \
   rm gradle-${GRADLE_VERSION}-bin.zip
ENV GRADLE_HOME /opt/gradle-${GRADLE_VERSION}
ENV PATH $PATH:$GRADLE_HOME/bin

FROM jdk8 as allure
# Install Allure CLI
RUN wget https://github.com/allure-framework/allure-core/releases/download/allure-core-1.4.23/allure-commandline.zip && \
   unzip allure-commandline.zip

FROM gradle as jars
# Prepare jars
WORKDIR ${MAIN_DIR}
COPY . .
RUN ./gradlew

FROM allure

WORKDIR ${MAIN_DIR}/build/libs
COPY --from=jars ${MAIN_DIR}/build/libs .
#Run tests, generate and open report
CMD (java -jar ${MAIN_JAR} || echo "Failed tests") && \
   allure generate -o allure-report allure-result && \
   allure report open -p 80
