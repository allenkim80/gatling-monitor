FROM grafana/grafana

USER root
RUN apt-get update && apt-get install -y curl gettext-base procps

WORKDIR /etc/grafana
COPY datasources ./datasources

WORKDIR /app
COPY entrypoint.sh ./
COPY dashboards ./
RUN chmod u+x entrypoint.sh
RUN chmod a+rwx gatling.json

ENTRYPOINT ["/app/entrypoint.sh"]