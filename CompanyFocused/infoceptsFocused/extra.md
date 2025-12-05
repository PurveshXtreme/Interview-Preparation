# Networking Notes

## Table of Contents
- [OSI Model – Short Notes](#osi-model--short-notes)
- [OSI Model (Bottom → Top)](#osi-model-bottom--top)
- [TCP vs UDP](#tcp-vs-udp)
- [What is HTTP?](#what-is-http)
- [What is an API?](#what-is-an-api)

---

## OSI Model – Short Notes
The OSI (Open Systems Interconnection) Model is a conceptual framework that standardizes how data travels across a network.  
It has **7 layers**, each with a specific function.

---

## OSI Model (Bottom → Top)

### **1. Physical Layer**
- Deals with raw bits transmission.  
- Includes cables, signals, connectors, hardware.

### **2. Data Link Layer**
- Provides error detection and MAC addressing.  
- Breaks data into frames.  
- Ensures reliable link between two directly connected devices.

### **3. Network Layer**
- Handles IP addressing and routing.  
- Determines the best path for data across networks.

### **4. Transport Layer**
- Provides end-to-end communication.  
- Uses **TCP (reliable)** or **UDP (fast)**.  
- Handles segmentation and flow control.

### **5. Session Layer**
- Manages sessions between two systems.  
- Opens, maintains, and closes communication sessions.

### **6. Presentation Layer**
- Handles data formatting, encryption, decryption, compression.  
- Ensures data is in a readable form for the application.

### **7. Application Layer**
- Closest to the user.  
- Provides network services like **HTTP, FTP, DNS, SMTP**.

---

## TCP vs UDP

### **TCP – Transmission Control Protocol**
- Connection-oriented  
- Reliable, ordered delivery  
- Error checking + retransmissions  
- Slower  
- Used in: **HTTP/HTTPS, Email, File Transfer**

### **UDP – User Datagram Protocol**
- Connectionless  
- Fast but not reliable  
- No retransmissions  
- Used in: **Video streaming, VoIP, Gaming, DNS**

---

## What is HTTP?
**HTTP (HyperText Transfer Protocol)** is a communication protocol used for sending and receiving data on the web.  
It defines how a **client (browser)** and a **server** communicate.

HTTP is:
- **Stateless** → the server does not remember previous requests  
- **Application Layer protocol** → Layer 7 of OSI  
- Used to transfer **HTML pages, images, data, API responses**, etc.

---

## What is an API?
**API (Application Programming Interface)** is a set of rules that allows two software applications to communicate with each other.

It defines:
- How data is requested  
- How data is sent  
- What format is used  

APIs allow the frontend and backend (or two different systems) to exchange information without needing to know each other's internal details.

