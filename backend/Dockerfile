FROM eclipse-temurin:21-jdk AS build
WORKDIR /app

ENV MAVEN_OPTS="-Xms64m -Xmx256m -XX:+UseSerialGC"

COPY . .
RUN chmod +x mvnw && ./mvnw -DskipTests package

FROM eclipse-temurin:21-jre
WORKDIR /app

COPY --from=build /app/target/*.jar app.jar

EXPOSE 8080

ENTRYPOINT ["java", "-Xms32m", "-Xmx160m", "-XX:+UseSerialGC", "-XX:MaxMetaspaceSize=160m", "-XX:ReservedCodeCacheSize=16m", "-XX:MaxDirectMemorySize=32m", "-jar", "app.jar"]
