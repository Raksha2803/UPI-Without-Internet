# UPI Without Internet

A Spring Boot-based simulation of offline UPI-style payments using a mesh network approach. The project demonstrates how encrypted payment packets can travel between virtual devices and reach a backend for validation and settlement when internet connectivity becomes available.

## Features

- **Offline Payment Simulation:** Simulates payment creation and transmission without an active internet connection on the sender device.
- **Mesh Network Simulation:** Uses virtual devices to propagate payment packets through gossip rounds.
- **Hybrid Encryption:** Uses RSA-OAEP and AES-GCM to protect payment data.
- **Duplicate Transaction Prevention:** Uses idempotency checks to prevent the same payment packet from being settled multiple times.
- **Secure Packet Validation:** Detects tampered packets and checks transaction freshness.
- **Transaction Management:** Maintains account balances and a transaction ledger.
- **Interactive Dashboard:** Provides a web interface to simulate payments and monitor the mesh network.

## Tech Stack

- Java 17
- Spring Boot
- Spring Data JPA
- Maven
- H2 In-Memory Database
- RSA-OAEP and AES-GCM
- HTML, CSS and JavaScript

## Getting Started

### Prerequisites

- JDK 17 or later
- Git

### Installation

Clone the repository:

```bash
git clone https://github.com/Raksha2803/UPI-Without-Internet.git
cd UPI-Without-Internet
```

### Run the Application

On Windows, run:

```powershell
.\mvnw.cmd spring-boot:run
```

On macOS or Linux, run:

```bash
./mvnw spring-boot:run
```

Once the application starts, open:

**http://localhost:8080**

## How It Works

1. Create a simulated payment by selecting the sender, receiver and amount.
2. Inject the encrypted payment packet into the virtual mesh network.
3. Run gossip rounds to simulate packet propagation between devices.
4. Upload packets through the simulated bridge device.
5. The backend validates the packet, prevents duplicate processing and settles valid transactions.
6. View the updated account balances and transaction ledger on the dashboard.

## Running Tests

Run the test suite using:

```powershell
.\mvnw.cmd test
```

The tests cover encryption and decryption, tampered packet rejection, and concurrent duplicate transaction handling.

## Limitations

This project is a proof-of-concept simulation. It does not use actual Bluetooth communication, connect to UPI or banking networks, or transfer real money. The mesh network and payment settlement are simulated locally.

