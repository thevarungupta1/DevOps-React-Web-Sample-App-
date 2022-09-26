# Dockererize React App


> FROM node:latest
The keyword here is FROM, our first step/instruction here says that we want to work with the latest node image.

> WORKDIR /app
WORKDIR here says that we want to add the source code of our application to the image. This line of instruction creates a directory called app in our image, and adds our source code to that directory.

> COPY package.json ./
In our application, we have installed some dependencies. COPY here copies the content of our packge.json file.

> RUN npm install
RUN npm install goes ahead to install all the dependencies we might have installed locally, in our image.

> COPY . .
What this does is it copies all the files in your local directory to the /app directory created in our image.

> CMD ["npm", "start"]
This final command starts up the application after every single step has been navigated successfully.


### create a image
> docker build -t react-web-sample-app:latest .

> docker image ls

> docker run -d -p 3000:3000 react-web-sample-app

> docker container ls