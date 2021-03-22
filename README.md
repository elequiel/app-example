
Create a file named Dockerfile in the same folder as the file package.json with the following contents.

`FROM node:12-alpine`
`RUN apk add --no-cache python g++ make`
`WORKDIR /app`
`COPY . .`
`RUN yarn install --production`
`CMD ["node", "src/index.js"]`

`docker build -t getting-started .`

`docker run -dp 3000:3000 getting-started`