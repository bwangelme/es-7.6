FROM elasticsearch:7.6.2

WORKDIR /usr/share/elasticsearch
COPY "plugins/elasticsearch-analysis-ik-7.6.2.zip" \
     "plugins/elasticsearch-analysis-pinyin-7.6.2.zip" \
     "plugins/analysis-icu-7.6.2.zip" "./"
Env PATH="/usr/share/elasticsearch/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
ENV ELASTIC_CONTAINER=true
RUN bin/elasticsearch-plugin install -b file:///usr/share/elasticsearch/elasticsearch-analysis-ik-7.6.2.zip && \
    bin/elasticsearch-plugin install -b file:///usr/share/elasticsearch/elasticsearch-analysis-pinyin-7.6.2.zip && \
    bin/elasticsearch-plugin install -b file:///usr/share/elasticsearch/analysis-icu-7.6.2.zip
ENTRYPOINT "/usr/local/bin/docker-entrypoint.sh"
CMD "eswrapper"
