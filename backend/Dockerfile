FROM node:22-alpine

WORKDIR /app

# Update Alpine security packages
RUN apk update && apk upgrade --no-cache

COPY package*.json ./

RUN npm ci

COPY . .

EXPOSE 3000

CMD ["npm", "start"] 