# Docker Compose Configuration for MongoDB and Mongo Express
## prep
- Docker : 
[Download & install from here !](https://docs.docker.com/desktop/)\

This Docker Compose configuration sets up two services: MongoDB and Mongo Express. MongoDB is a popular NoSQL database, and Mongo Express is a web-based administrative interface for MongoDB.

## Services

### MongoDB

- **Image**: mongo
- **Ports**: 27017:27017
- **Environment Variables**:
  - `MONGO_INITDB_ROOT_USERNAME`: Set to `username` for MongoDB root user.
  - `MONGO_INITDB_ROOT_PASSWORD`: Set to `password` for MongoDB root user's password.
- **Volumes**: 
  - `mymongo-data:/data/db`
  
### Mongo Express

- **Image**: mongo-express
- **Restart Policy**: Always
- **Ports**: 8081:8081
- **Environment Variables**:
  - `ME_CONFIG_MONGODB_ADMINUSERNAME`: Set to `username` for MongoDB admin user.
  - `ME_CONFIG_MONGODB_ADMINPASSWORD`: Set to `password` for MongoDB admin user's password.
  - `ME_CONFIG_MONGODB_SERVER`: Set to `mongodb` to connect to the MongoDB service defined in this Docker Compose file.

## Volumes

- **mymongo-data**: This volume is used by the MongoDB service to persist data stored in the `/data/db` directory.

## Usage

1. Ensure Docker and Docker Compose are installed on your system.
2. Create a directory for your project and place the `docker-compose.yml` file in it.
3. Open a terminal and navigate to the project directory.
4. Run the following command to start the services:
   ```bash
   docker-compose up -d

