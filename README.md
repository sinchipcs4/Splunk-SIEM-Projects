# Splunk-SIEM-Dashboard
# Splunk SIEM Dashboard Project

## Overview
This project demonstrates how Splunk can be used as a Security Information and Event Management (SIEM) tool to ingest logs, monitor key metrics, and visualize security-related events.  
By creating dashboards and panels, the goal was to gain actionable insights from real-time log data and detect potential anomalies.

---

## Objectives
- Install and configure Splunk
- Ingest data from log files or sources
- Build visual dashboards to monitor key metrics
- Derive actionable insights from real-time data

---

## Tools & Technologies
- Splunk Enterprise (Free Edition)
- Sample web server logs (Apache/Nginx)
- Virtual Machine environment
- SPL (Search Processing Language)

---

## Dashboard Panels Created
1. **Total Requests Over Time** – shows overall traffic trend.  
2. **Top Requested URLs (Paths)** – highlights most accessed endpoints.  
3. **HTTP Status Code Breakdown** – pie chart showing distribution of 2xx, 3xx, 4xx, 5xx codes.  
4. **Requests by Status Code Over Time** – line graph to track error spikes.  
5. **Large File Transfers** – identifies unusually large downloads/uploads.  
6. **Top Client IPs** – identifies most active clients/users by IP address.

---

## Methodology
1. Installed Splunk and set up the environment.  
2. Collected and ingested log files (web server access logs).  
3. Applied field extractions for HTTP methods, status codes, URIs, and IP addresses.  
4. Created SPL queries to filter and aggregate events.  
5. Built dashboards with multiple panels to visualize key security and traffic insights
