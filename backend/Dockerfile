FROM node:22-alpine

WORKDIR /app

# Update Alpine security packages
RUN apk update && apk upgrade --no-cache

COPY package*.json ./

# Install application dependencies
RUN npm ci

# Update npm to get newer bundled dependencies
RUN npm install -g npm@latest

COPY . .

EXPOSE 3000

CMD ["npm", "start"]