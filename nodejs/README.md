## prep
- Docker : 
[Download & install from here !](https://docs.docker.com/desktop/)
- nodejs : [Download & install from here !](https://nodejs.org/en/download)


## steps
- `npm init -y`
initializes the npm modules
- `npm i express`
used to install the Express.js framework for Node.js applications
-  `docker build -t anyname .` build the image with your desired name
- `docker container run -d -p 3000:3000 previously-given-name` this command will deploy the container on the port 3000 and will be accessible at your `machinesip:3000`
