# elasticsearch

Elasticsearch docker container

## Installation sur un public cloud ovh
Create DNS subdomain zones for letsencrypt HTTP challenge  
Install docker and docker-compose  
```bash
sudo apt install git
git clone git@github.com:tchartron/docker-elasticsearch.git
cd elasticsearch/
cd traefik/
mkdir letsencrypt
touch letsencrypt/acme.json
chmod 600 letsencrypt/acme.json
cp .env.example .env
docker-compose build
docker network create -d bridge elastic_network
docker-compose up -d
docker exec elastic_network /bin/bash -c "bin/elasticsearch-setup-passwords auto --batch --url http://elasticsearch:9200"
# Get password for kibana_system user from stdout and edit kibana.yml accordingly then restart the docker stack
```
