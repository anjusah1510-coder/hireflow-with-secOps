FROM node:22-alpine

WORKDIR /app

# Update Alpine security packages
RUN apk update && apk upgrade --no-cache

COPY package*.json ./

# Make npm more tolerant of transient network failures
RUN npm config set fetch-retries 5 \
    && npm config set fetch-retry-factor 2 \
    && npm config set fetch-retry-mintimeout 20000 \
    && npm config set fetch-retry-maxtimeout 120000 \
    && npm ci

COPY . .

EXPOSE 3000

CMD ["npm", "start"]