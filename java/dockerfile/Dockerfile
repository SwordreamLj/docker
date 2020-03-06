FROM maven:3.6.3-jdk-8

ENV GRADLE_HOME /opt/gradle
ENV GRADLE_VERSION 5.2.1

RUN set -o errexit -o nounset \
    && echo "Downloading Gradle" \
    && wget --no-verbose --output-document=gradle.zip "https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip" \
    && echo "Installing Gradle" \
    && unzip gradle.zip \
    && rm gradle.zip \
    && mv "gradle-${GRADLE_VERSION}" "${GRADLE_HOME}/" \
    && ln --symbolic "${GRADLE_HOME}/bin/gradle" /usr/bin/gradle \
    && echo "Testing Gradle installation" \
    && gradle --version
	
COPY settings.xml /usr/share/maven/conf/settings.xml
