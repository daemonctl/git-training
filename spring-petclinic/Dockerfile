FROM maven:3.8.6-openjdk-11 as builder
WORKDIR /spring-petclinic
COPY . .
RUN pwd
RUN mvn clean verify -Dmaven.test.skip=true
FROM emeraldsquad/sonar-scanner:latest 
WORKDIR /spring-petclinic
RUN ls
COPY --from=builder /spring-petclinic /spring-petclinic
RUN ls
RUN sonar-scanner