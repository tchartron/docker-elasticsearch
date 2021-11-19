ARG ELK_VERSION

# FROM docker.elastic.co/elasticsearch/elasticsearch:${ELK_VERSION}
FROM elasticsearch:${ELK_VERSION:-7.14.2}

COPY ./elasticsearch/elasticsearch.yml /usr/share/elasticsearch/config/elasticsearch.yml
# COPY ./elasticsearch/elasticsearch.yml /usr/share/elasticsearch/config/jvm.options

# Add your elasticsearch plugins setup here
# Example: RUN elasticsearch-plugin install analysis-icu
