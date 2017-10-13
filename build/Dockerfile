FROM node:8.7.0-alpine
RUN apk add --no-cache wget && mkdir -p /opt/inc/web
COPY src/ /opt/inc/web
WORKDIR /opt/inc/web
RUN npm install

# Install consul-template
RUN wget --no-check-certificate https://releases.hashicorp.com/consul-template/0.18.5/consul-template_0.18.5_linux_amd64.tgz -O /tmp/consul-tpl.tgz && \
  tar -zxvf /tmp/consul-tpl.tgz -C /usr/sbin && \
  chmod +x /usr/sbin/consul-template && \
  rm -f /tmp/consul-tpl.tgz

CMD ["npm","start"]

EXPOSE 3000
