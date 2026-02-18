# How to implement a docker Omeka instance (with fuseki)

The following instructions create a docker stack with Omeka, mysql and fuseki.
The MySQL container contains the database used by Omeka
The Fuseki image is useful to allow SPARQL query (the alternative built-in approach is extremely limited)

## Installation steps

Download the docker compose and env file from this repository
```shell
wget https://raw.githubusercontent.com/giobber/permea-documentation/refs/heads/main/docker/docker-compose.yaml
wget https://raw.githubusercontent.com/giobber/permea-documentation/refs/heads/main/docker/.env.default -O .env
```

Edit the `.env` file and create the container
```shell
docker compose up -d
```

Go to [http://localhost:8000] to see the newly created Omeka instance.
