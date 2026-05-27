# pull official base image
FROM node:22-alpine

# set working directory
WORKDIR /app

# add `/app/node_modules/.bin` to $PATH
ENV PATH /app/node_modules/.bin:$PATH

# install app dependencies
COPY package.json ./
COPY package-lock.json ./
RUN npm install --silent

# add app
COPY . ./
# Expose Vite port
EXPOSE 7775

# start app
CMD ["npm", "run", "dev", "--", "--host",  "0.0.0.0", "--port", "7775"]