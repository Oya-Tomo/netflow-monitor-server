# NetFlow Monitor Server

## Tech Stack

- Fluentd
- Elasticsearch
- Kibana

## Setup Instructions

```shell
docker compose up -d
```

## Accessing the Services

- Kibana: http://localhost:5601

## Check Elasticsearch

- To check if Elasticsearch has containing indices for NetFlow data, run the following command:

```shell
curl -X GET 'http://localhost:9200/_cat/indices?v'
```

## Testing with simulated NetFlow signals

```shell
sudo docker run -it --rm --network host networkstatic/nflow-generator -t localhost -p 5140
```
