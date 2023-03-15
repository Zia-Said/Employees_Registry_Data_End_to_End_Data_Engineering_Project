# Employee Data Pipeline
## This project is an end-to-end data engineering pipeline that registers employees' data in Cassandra database and then extracts, transforms, and stores the data locally for further analysis. The pipeline is built using Pyspark and Kafka with Zoopker.

### Prerequisites
Before you can run the pipeline, you need to have the following installed on your machine:

- Docker
- Docker Compose

### Installation
To install the required packages and build the Docker images, you can run the following command:

- docker-compose build

### Configuration
The configuration files are located in the config directory. Here's a brief overview of each file:

- cassandra.yaml: contains the configuration for Cassandra database
- kafka.yaml: contains the configuration for Kafka
- producer.yaml: contains the configuration for the Pyspark producer code
- consumer.yaml: contains the configuration for the Pyspark consumer code
- Make sure to update these files with the appropriate values for your environment.

### Running the Pipeline
To run the pipeline, you need to follow these steps:

1. Start Cassandra database and Kafka server by running the following command:
docker-compose up -d cassandra kafka

2. Start the Pyspark producer by running the following command:
docker-compose up -d producer
- This will read the employee data from Cassandra and publish it to Kafka.

3. Start the Pyspark consumer by running the following command:
docker-compose up -d consumer
-This will read the employee data from Kafka, perform some transformations, and store it locally.
