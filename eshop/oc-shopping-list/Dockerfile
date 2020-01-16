FROM openjdk:12

## Timezone
ENV TZ "Asia/Taipei"

## Java Options
ENV JDK_JAVA_OPTIONS "\
-Dfile.encoding=UTF-8 \
-Djavax.net.ssl.trustStore=/etc/ssl/truststore.jks \
-Djavax.net.ssl.trustStorePassword=password \
-javaagent:/newrelic/newrelic.jar \
"

## Copy Config file
ARG ENV
COPY /config/${ENV} /

## Copy and Run Application
COPY target/*.jar /application.jar
CMD ["java", "-jar", "application.jar"]