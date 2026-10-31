# Compila con Maven y JDK 21; la imagen final solo lleva el JRE y el jar.
FROM maven:3.9-eclipse-temurin-21 AS compilacion
WORKDIR /app
COPY pom.xml .
RUN mvn -q -B dependency:go-offline
COPY src src
RUN mvn -q -B package -DskipTests

FROM eclipse-temurin:21-jre
RUN useradd --system --no-create-home docentia
WORKDIR /app
COPY --from=compilacion /app/target/*.jar app.jar
USER docentia
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "app.jar"]
