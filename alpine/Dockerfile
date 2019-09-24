FROM node:alpine

# Install Gulp
RUN npm install -g gulp
RUN npm install gulp

# Change entrypoint
COPY docker-entrypoint.sh /docker-entrypoint.sh

ENTRYPOINT ["/bin/sh", "/docker-entrypoint.sh"]

CMD ["gulp", "watch"]