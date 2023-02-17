#Question - 
Fix a badly written Dockerfile. There is a conditional Node.js application, and a poorly written Dockerfile that will not be cached and will take up a lot of space. Need to rewrite it according to best-practice:


FROM ubuntu:18.04
COPY ./src /app
RUN apt-get update -y
RUN apt-get install -y nodejs
RUN npm install
ENTRYPOINT ["npm"]
CMD ["run", "prod"]


#Revised version of the Dockerfile -

1.Using an official Node.js base image (in this case, node:14-alpine) rather than Ubuntu to reduce image size.

2.Setting the working directory to /app.

3.Only copying the necessary files, which can speed up build time and reduce image size.

4.Installing only production dependencies (npm install --production) to further reduce image size.

5.Using the CMD instruction to set the default command for the container, rather than the ENTRYPOINT instruction, as it provides more flexibility.

6.With these changes, the new Dockerfile will be more efficient and cacheable, and the resulting image will be smaller and more appropriate for a production environment.
