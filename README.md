# 🚀 Apache Kafka Learning Lab (Codespaces-Optimized)

A minimal, resource-efficient Kafka learning environment designed for **GitHub Codespaces**.

## What's Inside

| Component | Details |
|-----------|---------|
| Kafka | 3.7 (KRaft mode — no ZooKeeper!) |
| UI | Redpanda Console (lightweight Kafka UI) |
| Language | Python with `confluent-kafka` |
| Infra | Docker Compose |

## 🏁 Quick Start

### Option 1: GitHub Codespaces (Recommended)
1. Click **"Code" → "Codespaces" → "Create codespace on main"**
2. Wait for the container to build (~2 min first time)
3. Everything is ready! Kafka starts automatically.

### Option 2: Local (with Docker)
```bash
docker compose up -d
pip install -r requirements.txt
```

## 📂 Project Structure

```
kafka-learning/
├── .devcontainer/          # Codespaces configuration
│   └── devcontainer.json
├── docker-compose.yml      # Kafka + Redpanda Console
├── lessons/
│   ├── 01_producer.py      # Your first producer
│   ├── 02_consumer.py      # Your first consumer
│   ├── 03_partitions.py    # Partitioning strategies
│   ├── 04_consumer_groups.py  # Consumer groups
│   ├── 05_avro_schema.py   # Schema & serialization
│   └── 06_streams_basic.py # Basic stream processing
├── scripts/
│   ├── start.sh            # Start Kafka
│   ├── stop.sh             # Stop Kafka
│   └── topic_admin.py      # Topic management utility
├── requirements.txt
└── README.md
```

## 🎓 Learning Path

| # | Lesson | Concepts |
|---|--------|----------|
| 1 | `01_producer.py` | Producing messages, keys, serialization |
| 2 | `02_consumer.py` | Consuming, offsets, auto-commit |
| 3 | `03_partitions.py` | Partition strategies, ordering guarantees |
| 4 | `04_consumer_groups.py` | Consumer groups, rebalancing |
| 5 | `05_avro_schema.py` | JSON schemas, data contracts |
| 6 | `06_streams_basic.py` | Stream processing with Faust |

## 🛠 Useful Commands

```bash
# Start/stop Kafka
./scripts/start.sh
./scripts/stop.sh

# List topics
python scripts/topic_admin.py list

# Create a topic
python scripts/topic_admin.py create my-topic --partitions 3

# Delete a topic
python scripts/topic_admin.py delete my-topic

# Open Redpanda Console (Kafka UI)
# → Port 8080 (auto-forwarded in Codespaces)
```

## 💡 Resource Usage

This setup is optimized for Codespaces free tier:
- **Kafka (KRaft)**: ~300-400MB RAM (no ZooKeeper overhead)
- **Redpanda Console**: ~50MB RAM
- **Total disk**: ~600MB for Docker images
- **CPU**: Minimal when idle

## ⚠️ Tips for Codespaces

- Stop Kafka when not in use: `./scripts/stop.sh`
- Codespaces auto-stops after 30min of inactivity (configurable)
- Your data persists between stops (Docker volumes)
- Use `docker compose down -v` to reset all Kafka data
