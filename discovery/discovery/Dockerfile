# Start with a base image containing Java runtime
FROM openjdk:11-jre-slim
# Add Maintainer Info
LABEL maintainer="DG-GL-FM-MDMServices@cevalogistics.com"

ENV APP_FILE masterdata-2.0.0-spring-boot.jar
ENV APP_HOME /usr/apps
ENV DEPTYPE="dev"

# Make ports available
EXPOSE 8080 8081

# Add the application's jar to the container
COPY --chown=nobody:nogroup target/$APP_FILE $APP_HOME/

# Run the jar file 
WORKDIR $APP_HOME

USER nobody

ENTRYPOINT ["sh", "-c"]
CMD ["exec java -Dspring.profiles.active=$DEPTYPE -jar $APP_FILE "]