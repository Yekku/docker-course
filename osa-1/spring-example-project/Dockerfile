FROM openjdk:8
COPY . /app
WORKDIR /app
RUN ./mvnw package
EXPOSE 8080
CMD java -jar ./target/docker-example-1.1.3.jar