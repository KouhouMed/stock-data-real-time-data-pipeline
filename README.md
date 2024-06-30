# Stock Market Real-Time Data Pipeline with Apache Kafka and Cassandra

This project implements a real-time data pipeline for stock market data using Apache Kafka and Cassandra. It consists of a Kafka producer that streams stock data, a Kafka consumer that reads this data, and a Cassandra database for storage.

## Project Components

1. `producer.py`: Kafka producer script that reads stock data from a CSV file and streams it to a Kafka topic.
2. `consumer.py`: Kafka consumer script that reads data from the Kafka topic and stores it in a Cassandra database.
3. `commands.sh`: Shell script containing instructions for setting up Kafka on an EC2 instance.

## Setup Instructions

### Kafka Setup on EC2

1. SSH into your EC2 instance.
2. Run the commands in `commands.sh` to:
   - Download and extract Apache Kafka
   - Install Java
   - Configure Kafka
   - Start ZooKeeper and Kafka server
   - Create a Kafka topic
   - Test the setup with console producer and consumer

### Cassandra Setup

1. Install Cassandra on your system or use a managed Cassandra service.
2. Ensure Cassandra is running and accessible from your EC2 instance.

## Usage

1. Ensure Kafka and Cassandra are running.
2. Run the producer script:
```
python producer.py
```

3. In a separate terminal, run the consumer script:
```
python consumer.py
```

## Configuration

- In both `producer.py` and `consumer.py`, replace `<Your Public IP>` with the public IP of your EC2 instance.
- Ensure the Cassandra connection details in `consumer.py` are correct for your setup.

## Dependencies

- Python 3.x
- kafka-python
- pandas
- cassandra-driver

Install the required Python packages:

```
pip install kafka-python pandas cassandra-driver
```