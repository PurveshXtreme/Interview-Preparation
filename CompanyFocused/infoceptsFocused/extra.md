# Networking Notes

## Table of Contents
- [OSI Model – Short Notes](#osi-model--short-notes)
- [OSI Model (Bottom → Top)](#osi-model-bottom--top)
- [TCP vs UDP](#tcp-vs-udp)
- [What is HTTP?](#what-is-http)
- [What is an API?](#what-is-an-api)

- # Cloud Concepts & Reporting Tools

## Table of Contents
- [Cloud Concepts](#cloud-concepts)
  - [What is Cloud Computing?](#what-is-cloud-computing)
  - [Cloud Service Models (IaaS, PaaS, SaaS)](#cloud-service-models-iaas-paas-saas)
  - [Deployment Models](#deployment-models)
  - [Advantages of Cloud](#advantages-of-cloud)
- [Reporting Tools](#reporting-tools)
  - [Power BI](#power-bi)
  - [Tableau](#tableau)
  - [Excel Pivot Tables](#excel-pivot-tables)

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

---

# Cloud Concepts & Reporting Tools

## Cloud Concepts (Short Notes)

### ⭐ What is Cloud Computing?
Cloud computing means delivering IT resources—like servers, databases, storage, and analytics—over the internet on a pay-as-you-go model.

### ⭐ Key Cloud Service Models
- **IaaS (Infrastructure as a Service)**  
  Provides virtual machines, networks, storage.  
  *Example: AWS EC2, Google Compute Engine.*

- **PaaS (Platform as a Service)**  
  Provides a platform to build and deploy applications without managing servers.  
  *Example: Heroku, Google App Engine.*

- **SaaS (Software as a Service)**  
  Ready-to-use software delivered over the internet.  
  *Example: Gmail, Office 365.*

### ⭐ Deployment Models
- **Public Cloud** – Shared cloud (AWS, Azure, GCP).  
- **Private Cloud** – Dedicated cloud for one organization.  
- **Hybrid Cloud** – Combination of public + private.

### ⭐ Advantages of Cloud
- Scalability  
- Cost-efficient (pay only for use)  
- High availability  
- Security  
- Global accessibility

---

## Reporting Tools

### ⭐ Power BI
- Microsoft’s business analytics tool.  
- Used to **visualize data**, build dashboards, and create reports.  
- Supports various data sources (Excel, SQL, APIs, cloud).  
- Strong interactive dashboards with DAX formulas.

### ⭐ Tableau
- A powerful data visualization tool.  
- Known for **drag-and-drop dashboards**, rich charts, and fast analytics.  
- Great for working with large datasets.  
- Used widely in BI and data analytics.

### ⭐ Excel Pivot Tables
- Used to **summarize and analyze data quickly**.  
- Helps perform grouping, filtering, totals, averages, and trends.  
- Useful for quick reporting without coding.  
- Often used for basic analytics and business reporting.

---

