FROM gradle:5.6.3-jdk12 as builder
COPY . /home/gradle/project
WORKDIR /home/gradle/project
RUN gradle build

FROM openjdk:12
RUN mkdir /app
COPY --from=builder /home/gradle/project/build/libs/hellowww-java-gradle-1.0.jar /app/hellowww.jar
WORKDIR /app
CMD ["java","-jar","-Dserver.port=80","hellowww.jar"]
