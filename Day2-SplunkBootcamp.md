# Splunk Bootcamp – Day 2 Recap  
*Understanding Splunk Architecture, Components, and Data Processing Pipeline*

---

## Overview  

Day 2 of the ThinkCloudly Splunk Bootcamp focused on the **architecture, setup, installation, and configuration** of Splunk. As someone pursuing a career in SOC analysis and threat hunting, this session helped me understand how data moves through Splunk's components—from ingestion to visualization—forming the foundation of a scalable, enterprise-grade SIEM system.

---

## Splunk Architecture

Splunk's architecture is modular and scalable, ranging from a single server setup for testing to multi-tiered enterprise deployments. The architecture consists of several core components:

- **Data Ingestion**: Collects logs from multiple sources such as servers, applications, databases, or devices.
- **Search Head**: Interfaces with the user to perform queries and visualize results.
- **Deployment Server**: Manages app and configuration distribution across Splunk instances.
- **Search Peers**: Enables distributed searching across indexed data for faster performance.
- **Indexer**: Parses and stores the data for retrieval and analysis.
- **Forwarders**: Transmit log data from source systems to the indexers.

---

## Splunk Data Lifecycle

### Data Input Stage  
Splunk consumes raw data from its source, splits it into 64K blocks, and tags each block with metadata like host, source, and sourcetype.

### Data Storage Stage  
1. **Parsing Phase**: Splunk processes raw logs into structured events.
   - Breaks logs into lines
   - Parses timestamps
   - Annotates events with metadata
   - Applies transformation rules using regex

2. **Indexing Phase**: Parsed data is compressed and written to disk, enabling fast retrieval during search.

### Data Searching Stage  
The search layer manages how users access and analyze the indexed data. It also stores knowledge objects like:
- Reports
- Alerts
- Dashboards
- Field extractions

---

## Core Splunk Components

### Splunk Forwarder  
Used to collect data from remote machines. There are two types:
- **Universal Forwarder**: Forwards raw data with minimal processing.
- **Heavy Forwarder**: Parses and filters data before sending it to the indexer, optimizing bandwidth.

### Splunk Indexer  
Transforms and stores data as events. It indexes data from forwarders and supports high-speed search operations.

### Splunk Search Head  
Provides a GUI for interacting with data. Users can perform searches, create reports, and visualize trends.

---

## Key Features of Splunk

- **Real-Time Indexing**: Allows immediate insight into data for rapid threat response.
- **Advanced Visualization**: Creates interactive dashboards for easy interpretation of anomalies and trends.
- **Cloning & Load Balancing**: Ensures high availability and data redundancy during transmission.

---

## Hands-On Observations

- We used the **standalone Splunk Enterprise installation** for desktop-based exploration.
- No forwarders were installed in this local setup since the logs were imported directly.
- Discussed the use of `inputs.conf` and `outputs.conf` in forwarder setups on Linux systems.
- Explored how Splunk receives data via network ports, file monitoring, and automated scripts.
- Reviewed the process of downloading Splunk Enterprise:  
    https://www.splunk.com/en_us/download/splunk-enterprise.html

---

## Licensing Models

We briefly touched on Splunk licensing, which includes:
- **Enterprise License**: Full features including authentication and distributed search.
- **Free License**: Limited indexing volume, basic features only.
- **Forwarder License**: Enables data forwarding, no indexing.
- **Beta/Premium App Licenses**: For testing or app-specific capabilities.

---

## Final Thoughts

This session gave me a deeper understanding of how Splunk operates behind the scenes. Grasping the architecture and flow of data across components like forwarders, indexers, and search heads is crucial for setting up an efficient SOC environment. As we move into dashboards and search queries tomorrow, this foundational knowledge will be invaluable.

Stay tuned for **Day 3**, where we dive into **Splunk architecture**, **deployment topologies**, and **real-world log ingestion scenarios**.
