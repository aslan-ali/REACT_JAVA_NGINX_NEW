FROM maven:3.6.3-jdk-11-slim AS builder
WORKDIR /app
COPY . /app
EXPOSE 8080
RUN mvn clean package -DskipTests

FROM openjdk:11-jre-slim
COPY --from=builder /app/target/*.jar /app.jar
RUN ls -ltr
CMD ["java","-jar","app.jar"]
