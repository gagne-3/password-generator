# Password Generator
An extremely simple docker container that spins up a webpage that displays a 16 character randomly generated password.

## Deployment
To deploy the container, there are two options:

## Docker Command
Open a terminal and run this:

```
docker run -d -p 6969:80 ghcr.io/gagne-3/password-generator:latest
```

After running this, the webpage will be accessible at `http://<your-server-ip>:6969`.

## Docker Compose
Alternatively, create a `docker-compose.yml` file and enter in the following:

```
version: '3'
services:
  random-password-webpage:
    image: ghcr.io/gagne-3/password-generator:latest
    ports:
      - "6969:80"
    restart: unless-stopped
```

Once the file is created, run the following command from the directory containing `docker-compose.yml`:

```
docker-compose up -d
```

This will start the container in detached mode, making the webpage accessible via `http://<your-server-ip>:6969`.