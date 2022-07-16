FROM openjdk:8-jdk-alpine as build
ARG VERSION=3.8.6
WORKDIR /app
RUN wget https://downloads.apache.org/maven/maven-3/$VERSION/binaries/apache-maven-$VERSION-bin.zip
RUN unzip apache-maven-$VERSION-bin.zip
RUN rm -rf apache-maven-$VERSION-bin.zip
ENV MAVEN_HOME=/app/apache-maven-$VERSION
ENV PATH="$MAVEN_HOME/bin:$PATH"
COPY . .
RUN mvn clean verify sonar:sonar -Dsonar.projectKey=java -Dsonar.host.url=http://192.168.0.108:9000  -Dsonar.login=sqp_c778cae3730a351123caef34bded83254b517e48
RUN mvn clean package

FROM openjdk:8-jre-alpine
WORKDIR /app
COPY --from=build /app/target/hello-world-rest-api.jar .
EXPOSE 8082
CMD ["java","-jar","hello-world-rest-api.jar"]
