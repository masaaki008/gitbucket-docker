FROM java:8-jre

ADD https://github.com/gitbucket/gitbucket/releases/download/4.34.0/gitbucket.war /opt/gitbucket.war
ADD https://github.com/mrkm4ntr/gitbucket-network-plugin/releases/download/1.8.0/gitbucket-network-plugin_2.13-1.8.0.jar /gitbucket-plugins/gitbucket-network-plugin_2.13-1.8.0.jar
ADD https://github.com/gitbucket-plugins/gitbucket-explorer-plugin/releases/download/8.0.0/gitbucket-explorer-plugin-8.0.0.jar /gitbucket-plugins/gitbucket-explorer-plugin-8.0.0.jar
ADD https://github.com/kasancode/gitbucket-label-kanban-plugin/releases/download/3.6.0/gitbucket-label-kanban-plugin-3.6.0.jar /gitbucket-plugins/gitbucket-label-kanban-plugin-3.6.0.jar
ADD https://github.com/kasancode/gitbucket-gantt-plugin/releases/download/1.1.0/gitbucket-ganttchart-plugin-1.1.0.jar /gitbucket-plugins/gitbucket-ganttchart-plugin-1.1.0.jar

RUN ln -s /gitbucket /root/.gitbucket

VOLUME /gitbucket

EXPOSE 20000
EXPOSE 29418

ENV MAX_FILE_SIZE=3145728
ENV PLUGINS_DIR=/gitbucket-plugins

CMD ["sh", "-c", "java -jar /opt/gitbucket.war --plugin_dir=$PLUGINS_DIR --max_file_size=$MAX_FILE_SIZE"]
