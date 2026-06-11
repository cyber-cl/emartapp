FROM maven:3.9-eclipse-temurin-8 AS BUILD_IMAGE
WORKDIR /usr/src/app/
COPY ./ /usr/src/app/
RUN mvn install -DskipTests

FROM maven:3.9-eclipse-temurin-8

WORKDIR /usr/src/app/
COPY --from=BUILD_IMAGE /usr/src/app/target/book-work-0.0.1-SNAPSHOT.jar ./book-work-0.0.1.jar

EXPOSE 9000
ENTRYPOINT ["java","-jar","book-work-0.0.1.jar"]
# Test  