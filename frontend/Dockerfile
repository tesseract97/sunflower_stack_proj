# Pull latest official node image
FROM node:14.16.0

#Expose ports
# Port 3000 is where we access our web app in the browser
# Port 35729 necessary for hot reloading
EXPOSE 3000
EXPOSE 35729

#Set Working Directory
WORKDIR /app

#Add /app/nnode_modules/.bin to environment variables
ENV PATH /app/node_modules/.bin:$PATH

#Copy package files and install app dependencies
COPY package.json /app/package.json
COPY package-lock.json /app/package-lock.json
RUN npm install
RUN npm install react-scripts -g

# Add React app to working directory
ADD . /app
#Start the React app
CMD ["npm", "start"]