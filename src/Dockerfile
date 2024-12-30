FROM maven:amazoncorretto AS build
WORKDIR /app
COPY  /app/* /usr/app/
RUN mvn clean -f /usr/app/pom.xml install

FROM mlkrtk/tomcat-final 
COPY --from=build /usr/app/target/*.war /usr/local/tomcat/webapps/
