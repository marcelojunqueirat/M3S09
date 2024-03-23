#postgres
FROM postgres:16.1
LABEL maintainer="admin@admin.com"
ENV POSTGRES_USER=postgres
ENV POSTGRES_PASSWORD=1234
ENV POSTGRES_DB=postgres
EXPOSE 5432

#pgadmin
FROM dpage/pgadmin4:latest
ENV PGADMIN_DEFAULT_EMAIL=admin@pgadmin.org
ENV PGADMIN_DEFAULT_PASSWORD=admin
EXPOSE 80

#backend
FROM eclipse-temurin:17-jdk-jammy
WORKDIR /app
COPY .mvn/ .mvn
COPY mvnw pom.xml ./
RUN chmod +x mvnw
RUN ./mvnw dependency:resolve
COPY src ./src


CMD ["sh", "-c", "./mvnw spring-boot:run && ./usr/local/bin/start.sh"]
