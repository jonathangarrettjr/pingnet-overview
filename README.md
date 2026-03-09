# pingnet-overview

**Decentralized Safety Communication Mesh for Vehicles, Drones, and Infrastructure**

PingNet is a local-first mesh networking platform designed to improve situational awareness and coordination between vehicles, unmanned aerial systems (UAS), infrastructure nodes, and human drivers.

The system enables safety-critical data to propagate locally across nearby participants **without requiring cellular networks, GPS connectivity, or centralized infrastructure**.

PingNet is designed for environments where traditional communication systems degrade or fail:

- tunnels
- dense urban areas
- disaster zones
- remote infrastructure
- GPS-denied environments

The goal is to create a **resilient safety communication layer** that complements existing mobility systems.

# System Overview

PingNet nodes form a local mesh network that allows vehicles, drones, and infrastructure to exchange safety-critical data in real time.

## High-Level Architecture
```text
            +-------------------+
            |  Roadside Unit    |
            |    (RSU Node)     |
            +---------+---------+
                      |
                      |
        +-------------+-------------+
        |                           |
  +-----+------+              +-----+------+
  | Vehicle    |              | Vehicle    |
  |  Node      |              |  Node      |
  |  (Car)     |              |  (Car)     |
  +-----+------+              +-----+------+
        |                           |
        |        Local Mesh         |
        |     (Wi-Fi / BLE)         |
        |                           |
  +-----+------+              +-----+------+
  | EMS /      |              | Construction|
  | Safety     |              |    Node     |
  |   Node     |              |             |
  +-----+------+              +-----+------+
        |
        |
  +-----+------+
  | Drone /    |
  |   UAS Node |
  +------------+
```

Nodes communicate directly over short-range transports such as Wi-Fi or Bluetooth.

Each node can:

- broadcast hazards
- relay safety messages
- verify cryptographic signatures
- participate in distributed trust decisions
- propagate crisis alerts

The mesh operates without requiring cellular networks or centralized infrastructure.

---

# Core Idea

Modern mobility systems depend heavily on centralized infrastructure:

- cellular networks  
- GPS  
- cloud routing  

These systems work well in normal conditions but degrade in environments where connectivity is unreliable.

PingNet introduces a **local safety communication layer** where nearby participants share critical information directly using short-range transports such as:

- Wi-Fi  
- Bluetooth Low Energy  
- optional C-V2X integration  
- optional cellular bridge  

Nodes form a **temporary distributed mesh**, propagating safety information across the local environment.

---

# What PingNet Enables

PingNet supports multiple safety and coordination capabilities.

## Hazard Propagation

Nodes detect hazards and broadcast alerts to nearby participants.

Examples:

- debris on roadway  
- sudden braking events  
- fog or environmental hazards  
- stalled vehicles  

Messages propagate across the mesh to increase awareness beyond line-of-sight.

---

## Predictive Collision Awareness

Vehicles exchange motion vectors such as:

- position  
- velocity  
- direction  

Nodes can identify potential collision paths before impact and alert nearby participants.

---

## Emergency Priority Signaling

Emergency vehicles or responders broadcast **priority messages** that propagate with elevated priority across the mesh.

Nearby participants can react automatically.

---

## Infrastructure-Free Coordination

PingNet continues operating even when:

- cellular networks fail  
- GPS is degraded  
- centralized services are unavailable  

Nodes rely on local communication and distributed trust verification.

---

# Technical Architecture

PingNet nodes participate in several core processes.

## Peer Discovery

Nodes discover nearby participants using available wireless transports.

---

## Message Propagation

Messages are propagated across the mesh using controlled relay mechanisms.

Key considerations include:

- duplicate suppression  
- message TTL limits  
- rate limiting  
- congestion control  
- priority routing  

---

## Distributed Trust

Each message is cryptographically signed.

Nodes evaluate trust through:

- signature verification  
- short-lived pseudonym credentials  
- behavioral trust scoring  
- local voting to isolate malicious nodes  

This approach avoids reliance on centralized revocation lists while maintaining message authenticity.

---

## Crisis Mode

Nodes can enter a **crisis state** when a severe incident occurs.

Examples include:

- vehicle collision  
- catastrophic system fault  
- manual emergency trigger  

Crisis alerts propagate with the highest priority and require acknowledgment from emergency nodes.

Propagation is controlled to prevent congestion or abuse.

---

# Current Development Focus

PingNet development is currently focused on the following areas.

## Mesh Runtime

Rust-based runtime responsible for:

- message propagation  
- relay logic  
- duplicate detection  
- priority scheduling  
- trust validation  

Key technologies:

- Rust  
- Tokio async runtime  
- UDP multicast  
- cryptographic message signing  

---

## Transport Abstraction

PingNet aims to support multiple transports through a unified abstraction layer.

Primary transports:

- Wi-Fi  
- Bluetooth Low Energy  

Optional transports:

- C-V2X  
- cellular bridge  

---

## Swarm Simulation

Large-scale simulations test behavior under conditions such as:

- large node counts  
- network partitions  
- malformed messages  
- replay attacks  
- node failure  

---

# Why This Is an Interesting Engineering Problem

PingNet combines several challenging systems problems:

- distributed systems  
- mesh networking  
- wireless coexistence  
- failure-mode engineering  
- safety-critical messaging  
- adversarial resilience  

The platform must function reliably even when infrastructure is unavailable and network conditions are unpredictable.

---

# Looking to Connect With Engineers Interested In

- Rust async systems  
- distributed networking  
- congestion control  
- peer-to-peer protocols  
- safety-critical communication  
- resilient infrastructure design  

PingNet is currently exploring collaborations with engineers interested in **hard distributed systems problems in real-world environments**.

---

# MVP Demonstration

PingNet currently includes a working proof-of-concept mesh network deployed on Raspberry Pi hardware.

The MVP demonstrates:

- multi-node hazard propagation
- signed safety message exchange
- distributed relay behavior
- role-based priority messaging

### Hardware Testbed

The prototype test environment uses a six-node Raspberry Pi mesh including:

- 2x Vehicle nodes
- Emergency services node
- Construction zone node
- UAS / drone relay node
- Console / map visualization node

These nodes communicate over a local wireless mesh and relay safety alerts between participants.

<img width="1509" height="1013" alt="image" src="https://github.com/user-attachments/assets/ddf809a9-a6a0-4694-9fbe-bcd4562e4604" />

*Six-node PingNet MVP testbed demonstrating vehicle, EMS, construction, and UAS nodes participating in a local safety mesh network. Console node not pictured.*

---

# Customer Discovery

PingNet development has been informed by interviews with transportation leaders and industry participants.

Stakeholders consulted include:

- Utah Department of Transportation
- Delaware Department of Transportation
- Maricopa County DOT
- Eastern Transportation Coalition

Research findings highlight several key challenges for V2X deployment:

- low vehicle equipage
- funding constraints
- standards uncertainty
- the need for trustworthy safety alerts

These insights guide PingNet’s focus on infrastructure-independent safety communication.

---

# Contact

**Jonathan Garrett Jr.**  
Founder — PingNet

Email: jonathan.garrettjr@pingnet.net  
Website: https://www.pingnet.net  
LinkedIn: https://www.linkedin.com/in/jonathan-garrett-jr

---

# Notes

PingNet is currently under active development. Some components and designs described here may evolve as the system matures.
