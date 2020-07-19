FROM influxdb:1.7.9

# ADD influxdb-selfsigned.key /etc/ssl/influxdb-selfsigned.key

# ADD influxdb-selfsigned.crt /etc/ssl/influxdb-selfsigned.crt

RUN openssl req -x509 -nodes -newkey rsa:2048 \
  -keyout /etc/ssl/influxdb-selfsigned.key \
  -out /etc/ssl/influxdb-selfsigned.crt \
  -days 3650 \
  -subj /CN=test.com

RUN chown influxdb:influxdb /etc/ssl/influxdb-selfsigned.*

ADD influxdb.conf /etc/influxdb/influxdb.conf

ENV INFLUXDB_HTTP_AUTH_ENABLED=true