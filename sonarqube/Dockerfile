FROM sonarqube:7.9.6-community

USER root
RUN apt-get update && apt-get install -y wget --no-install-recommends && rm -rf /var/lib/apt/lists/*
RUN wget -q https://github.com/dependency-check/dependency-check-sonar-plugin/releases/download/2.0.7/sonar-dependency-check-plugin-2.0.7.jar -P /opt/sonarqube/extensions/plugins
RUN wget -q https://github.com/spotbugs/sonar-findbugs/releases/download/4.0.3/sonar-findbugs-plugin-4.0.3.jar -P /opt/sonarqube/extensions/plugins
RUN wget -q https://github.com/Coveros/zap-sonar-plugin/releases/download/sonar-zap-plugin-2.2.0/sonar-zap-plugin-2.2.0.jar -P /opt/sonarqube/extensions/plugins

USER sonarqube
ENTRYPOINT ["/opt/sonarqube/bin/run.sh"]
