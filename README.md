# NetPulse

**NetPulse** is a collaborative network monitoring and diagnostics platform designed to explore practical **telecommunications, computer networking, and network automation** concepts using **Go and Python**.

The project simulates a network operations environment where network nodes can be monitored, measured, analysed, and diagnosed through software-based network tools.

> **Project status:** 🚧 Early Development

---

## 🎯 Project Goals

NetPulse aims to provide a practical platform for:

* Network discovery
* Connectivity monitoring
* Latency and packet-loss measurement
* Network performance monitoring
* Packet and protocol analysis
* Network troubleshooting
* QoS/KPI monitoring
* Network topology discovery
* Network anomaly detection
* Network automation

The project is designed to run primarily in a **virtual network laboratory**, so physical routers and switches are not required.

---

## 🏗️ High-Level Architecture

```text
                         Virtual Network
                               │
                ┌──────────────┼──────────────┐
                │              │              │
             Node A          Router          Node B
                │              │              │
                └──────────────┼──────────────┘
                               │
                 ┌─────────────┴─────────────┐
                 │                           │
          ┌──────▼──────┐             ┌──────▼──────┐
          │  Go Agent   │             │Python Agent │
          │             │             │             │
          │ Discovery   │             │Packet       │
          │ Probing     │             │Analysis     │
          │ Monitoring  │             │Traffic      │
          │ Topology    │             │Analysis     │
          └──────┬──────┘             └──────┬──────┘
                 │                           │
                 └─────────────┬─────────────┘
                               │
                         Data / API Layer
                               │
                         ┌─────▼─────┐
                         │ Dashboard │
                         └───────────┘
```

---

## 👥 Team Responsibilities

### Go — Network Engine

The Go component is responsible for active network operations and network infrastructure functions.

Planned responsibilities include:

* CIDR/subnet processing
* Host discovery
* ICMP/network probing
* TCP/UDP connectivity checks
* Port monitoring
* Latency measurement
* Packet-loss measurement
* Network topology discovery
* Network monitoring scheduler
* Network API
* Concurrent network operations

Go will serve as the primary **network measurement and monitoring engine**.

---

### Python — Network Analysis Engine

The Python component will also perform networking tasks, with emphasis on packet-level analysis and network intelligence.

Planned responsibilities include:

* Packet capture
* Protocol analysis
* Traffic analysis
* SNMP-based monitoring
* Network statistics
* QoS analysis
* Anomaly detection
* Network performance analysis
* Reporting and visualization

Python will serve as the **network analysis and intelligence layer**.

---

## 🌐 Networking Scope

NetPulse will focus on practical networking concepts including:

### Network Layer

* IPv4
* CIDR
* Subnetting
* Routing
* ICMP
* Network topology

### Transport Layer

* TCP
* UDP
* Ports
* Connection establishment
* Packet loss
* Latency
* Jitter

### Application Layer

* DNS
* HTTP/HTTPS
* Network service monitoring

### Network Management

* SNMP
* Network KPIs
* Monitoring
* Performance measurement
* Fault detection

---

## 📊 Network KPIs

NetPulse will monitor and analyse metrics such as:

| KPI                 | Description                                                |
| ------------------- | ---------------------------------------------------------- |
| Latency             | Time required for packets to travel between endpoints      |
| Packet Loss         | Percentage of packets that fail to reach their destination |
| Jitter              | Variation in packet delay                                  |
| Throughput          | Amount of data transferred over a period                   |
| Availability        | Percentage of time a network service is reachable          |
| DNS Response Time   | Time required to resolve a domain                          |
| TCP Connection Time | Time required to establish a TCP connection                |

These metrics will be useful for studying **network performance and QoS**.

---

## 🧪 Virtual Network Laboratory

Because the project does not depend on physical networking hardware, the network environment can be simulated using:

* Docker
* Linux network namespaces
* Mininet
* FRRouting
* Virtual machines
* Wireshark
* tcpdump

Example topology:

```text
                    Router
                   /      \
                  /        \
             Network A   Network B
                /            \
             Host A          Host B
                \            /
                 NetPulse
```

The laboratory can later introduce controlled network conditions such as:

* Increased latency
* Packet loss
* Bandwidth limitations
* Link failures
* Network congestion

This allows the monitoring and analysis components to be tested against realistic network scenarios.

---

## 🔌 Go ↔ Python Integration

The Go and Python components will communicate through a defined interface.

Initial data exchange may use JSON over HTTP.

Example:

```json
{
  "timestamp": "2026-09-24T14:30:00Z",
  "source": "10.0.0.2",
  "destination": "10.0.0.3",
  "latency_ms": 12.4,
  "packet_loss": 0.0,
  "jitter_ms": 2.1
}
```

The API contract will be documented separately so both components can be developed independently.

---

## 📁 Project Structure

```text
netpulse/
│
├── go-agent/                  # Go network engine
│   ├── cmd/
│   ├── internal/
│   └── README.md
│
├── python-agent/              # Python network analysis engine
│   ├── analysis/
│   ├── packet_capture/
│   └── README.md
│
├── network-lab/               # Virtual network environment
│   ├── topology/
│   ├── docker/
│   └── configs/
│
├── docs/                      # Project documentation
│   ├── architecture/
│   ├── api/
│   └── network-design/
│
├── tests/
│
├── docker-compose.yml
├── .gitignore
└── README.md
```

---

## 🚀 Development Roadmap

### Phase 1 — Network Discovery

* [ ] Initialize Go network engine
* [ ] CIDR parsing
* [ ] Generate host addresses
* [ ] Host discovery
* [ ] Basic connectivity testing

### Phase 2 — Network Performance

* [ ] Latency measurement
* [ ] Packet-loss measurement
* [ ] TCP connectivity checks
* [ ] UDP testing
* [ ] DNS monitoring

### Phase 3 — Network Analysis

* [ ] Python packet capture
* [ ] Protocol identification
* [ ] Traffic statistics
* [ ] Network KPI analysis

### Phase 4 — Network Topology

* [ ] Network topology representation
* [ ] Device discovery
* [ ] Route/path analysis
* [ ] Topology visualization

### Phase 5 — Network Management

* [ ] SNMP monitoring
* [ ] Network device metrics
* [ ] Fault detection
* [ ] Network alerts

### Phase 6 — Integration

* [ ] Go REST/gRPC API
* [ ] Python integration
* [ ] Shared data model
* [ ] Central database
* [ ] Monitoring dashboard

### Phase 7 — Advanced Networking

* [ ] QoS analysis
* [ ] Traffic anomaly detection
* [ ] Network failure simulation
* [ ] Automated diagnostics
* [ ] Network automation

---

## 🛠️ Planned Technology Stack

### Core

* Go
* Python
* Linux
* Git/GitHub

### Networking

* TCP/IP
* ICMP
* UDP
* DNS
* HTTP/HTTPS
* SNMP

### Virtualisation & Laboratory

* Docker
* Linux network namespaces
* Mininet
* FRRouting

### Monitoring & Observability

* Prometheus
* Grafana

### Packet Analysis

* Wireshark
* tcpdump
* Python networking libraries

---

