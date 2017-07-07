FROM openjdk:8

ENV API_KEY=""

# Install datadog agent
RUN apt-get update
RUN apt-get install apt-transport-https
RUN  sh -c "echo 'deb https://apt.datadoghq.com/ stable main' > /etc/apt/sources.list.d/datadog.list"
RUN  apt-key adv --keyserver keyserver.ubuntu.com --recv-keys C7A7DA52
RUN  apt-get update
RUN  apt-get install datadog-agent
RUN  sh -c "sed 's/api_key:.*/api_key: ${API_KEY}/' /etc/dd-agent/datadog.conf.example > /etc/dd-agent/datadog.conf"

# Copy over prod files
VOLUME ["/usr/src/myapp"]
COPY . /usr/src/myapp
WORKDIR /usr/src/myapp

# Run the scala play bash script
CMD ["bash", "bin/play_scala_rest_framework"