# Splunk-SIEM-Dashboard Projects

## Overview
This project demonstrates how Splunk can be used as a Security Information and Event Management (SIEM) tool to ingest logs, monitor key metrics, and visualize security-related events.  
By creating dashboards and panels, the goal was to gain actionable insights from real-time log data and detect potential anomalies.


## Objectives
- Install and configure Splunk[Splunk_Dashboard_PPT.pptx](https://github.com/user-attachments/files/22516577/Splunk_Dashboard_PPT.pptx)

- Ingest data from log files or sources
- Build visual dashboards to monitor key metrics
- Derive actionable insights from real-time data


## Tools & Technologies
- Splunk Enterprise (Free Edition)
- Sample web server logs (Apache/Nginx)
- Virtual Machine environment
- SPL (Search Processing Language)


## Dashboard Panels Created
1. **Total Requests Over Time** – shows overall traffic trend.  
2. **Top Requested URLs (Paths)** – highlights most accessed endpoints.  
3. **HTTP Status Code Breakdown** – pie chart showing distribution of 2xx, 3xx, 4xx, 5xx codes.  
4. **Requests by Status Code Over Time** – line graph to track error spikes.  
5. **Large File Transfers** – identifies unusually large downloads/uploads.  
6. **Top Client IPs** – identifies most active clients/users by IP address.
   1. Total Requests Over Time
index=weblogs | timechart count span=1h


Explanation: Counts all web requests per hour and visualizes traffic trends over time. Useful to monitor overall activity patterns and detect traffic spikes.

2. Top Requested URLs (Paths)
index=weblogs | stats count by uri_path | sort - count

Explanation: Aggregates the most accessed URLs/paths. Helps identify which pages or resources are most frequently requested.

3. HTTP Status Code Breakdown
index=weblogs | stats count by status | sort - count

Explanation: Counts occurrences of each HTTP status code. Useful for spotting errors (4xx, 5xx) or unusual activity.

4. Requests by Status Code Over Time
index=weblogs | timechart count by status span=1h

Explanation: Shows how different status codes trend over time. Helps detect spikes in errors or suspicious patterns.

5. Large File Transfers
index=weblogs | where bytes>1000000 | stats count by uri_path, clientip

Explanation: Filters requests with large payloads (e.g., >1MB). Identifies potentially risky downloads/uploads for monitoring.

6. Top Client IPs
index=weblogs | stats count by clientip | sort - count

Explanation: Aggregates the most active client IPs. Helps detect heavy users or suspicious IPs accessing the system.


## Methodology
1. Installed Splunk and set up the environment.  
2. Collected and ingested log files (web server access logs).  
3. Applied field extractions for HTTP methods, status codes, URIs, and IP addresses.  
4. Created SPL queries to filter and aggregate events.  
5. Built dashboards with multiple panels to visualize key security and traffic insights

## Conclusion
Establishing this dashboard gave us a clear picture of client behavior, popular content, and online traffic trends.
It emphasized how error spikes and HTTP status patterns can point to setup or performance problems. 
Large file transfers and top IPs were monitored to provide insight into user impact and possible threats.
In general, the dashboard makes it possible to resolve issues more quickly and make data-driven decisions to maximize web server performance


   

