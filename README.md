# 🛡️ SOC Home Lab

Welcome to my **SOC Home Lab** repository! This lab demonstrates a full Security Operations Center environment, including detection engineering, log analysis, incident response, and network monitoring. The lab is broken into modular steps so you can follow along and replicate a real-world SOC setup.

---

## 🎯 Lab Objectives

By completing this lab, you will learn to:

- Configure **Advanced Audit Policies** on Windows endpoints  
- Deploy **Sysmon** for endpoint process monitoring  
- Install and configure **Suricata IPS** in IPS mode  
- Set up **Zeek** for network flow monitoring and JSON logging  
- Deploy **Arkime** for network packet capture and analysis  
- Implement a **FIR ticketing system** for incident management  
- Install and configure **Splunk Enterprise** with forwarders for log ingestion  

---

## 🗂️ Table of Contents

1. [Advanced Audit Policy Configuration](01_Advanced_Audit_Policy/README.md)  
   Learn how to configure Windows audit policies, PowerShell logging, and RPC event tracking.

2. [Sysmon Deployment](02_Sysmon/README.md)  
   Steps to install and configure Sysmon, including XML configuration and service verification.

3. [Suricata IPS](03_Suricata_IPS/README.md)  
   Guide to installing Suricata, configuring IPS mode, updating rulesets, and verifying operation.

4. [Zeek NetFlow](04_Zeek_NetFlow/README.md)  
   Instructions for setting up Zeek, configuring interfaces, network monitoring, JSON log output, and Splunk forwarder integration.

5. [Arkime Packet Capture](05_Arkime/README.md)  
   Deploy Arkime for packet capture, dashboard setup, and basic configuration.

6. [FIR Ticketing System](06_FIR_Ticketing/README.md)  
   Install and configure the FIR ticketing system for incident tracking and management.

7. [Splunk Deployment](07_Splunk_Deployment/README.md)  
   Install Splunk Enterprise, configure web settings, enable SSL, and add forwarders.

---

## ⚡ Tips for Using This Lab

- Follow the steps **in order** to avoid errors.  
- Each folder contains **detailed instructions**, **commands**, and screenshots.  
- Use the TOC links to jump directly to each section.  
- Combine this guide with your own hands-on testing for best learning results.  

---

> 🎉 Completing this lab will give you practical experience in building a SOC environment, configuring endpoints, monitoring network traffic, and analyzing logs for security events. Perfect for aspiring SOC Analysts or Security Engineers.
