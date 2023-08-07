# Elasticsearch-Filebeat-Kibana Docker Cluster

This repository contains a Docker Compose configuration for setting up a scalable Elasticsearch, Kibana, and Filebeat cluster. The cluster is designed to collect, store, and visualize logs from Docker containers.

## Prerequisites

- Docker and Docker Compose are installed on the host machine.
- Internet connectivity to download Docker images from Docker Hub.

## Getting Started

1. Clone this repository:

```bash
git clone https://github.com/bhaveshs6/efk-stack-docker.git
cd efk-stack-docker
```

2. Customize the .env file:

Edit the .env file and set the desired environment variables. Make sure to set strong passwords for security-sensitive variables.

3. Start the cluster:

```bash
docker-compose up -d
```

This command will start Elasticsearch, Kibana, and Filebeat containers with the configurations defined in the docker-compose.yml file.

### Access Kibana:

Open your web browser and navigate to http://localhost:5601. Kibana will be accessible through this URL, and you can use it to visualize and analyze the logs collected by Filebeat.

## Scaling the Cluster

To scale the Elasticsearch cluster, you can use the docker-compose scale command. For example, to add two additional Elasticsearch nodes:

```bash
docker-compose up -d --scale es01=3
```

This will add two more Elasticsearch nodes, and the cluster will automatically rebalance the shards to distribute the data across the nodes.

## Monitoring and Troubleshooting

To view the logs of individual containers:

```bash
docker-compose logs -f <container-name>
```

## Clean Up

To stop and remove the containers:

```bash
docker-compose down
```

## Security Considerations

- Make sure to set strong passwords for all sensitive variables (`ELASTIC_PASSWORD`, `KIBANA_PASSWORD`, etc.) to prevent unauthorized access to your cluster.
- Consider configuring a reverse proxy (e.g., Nginx) to add an extra layer of security for accessing Kibana and Elasticsearch.

## License

This project is licensed under the [MIT License](LICENSE).
