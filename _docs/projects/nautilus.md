---
title: Nautilus
description: NAVAL Systems
---

##### xFusionCorp
123 Marvis Bay
Syldavia

# Project Nautilus

## OVERVIEW
Project Nautilus is run by the Naval subdivision within xFusionCorp Industries.
The Nautilus Application helps the Naval forces to make smart procurement decisions on manned and unmanned maritime systems while ensuring that operational requirements are met. It aims to provide best in class operational support, improve the safety and life extension of existing machines, and reduce cost of ownership.

## Current Repertoire
1. Sonar Technology and Systems
2. LUSV - Large Unmanned Surface Vehicles
3. Autonomous Unmanned Undersea Pods
4. Nuclear Submarines
5. Laser Guidance Systems

## Application Architecture
Nautilus deployment architecture can be viewed [here](https://www.lucidchart.com/documents/edit/58e22de2-c446-4b49-ae0f-db79a3318e97/0_0?shared=true)

The Nautilus is a three-tier application and is deployed in the Stratos Datacenter in the North America Region.

 - **Data Tier:** The Data tier is the layer that stores data with the retrieval storage and execution methods made by the application layer. We are making use of MariaDB which is one of the most popular open source relational databases.

 - **Application Tier:** Makes use of a LAMP which is a stack of open-source software that can be used to create web applications. LAMP is an acronym that usually consists of the Linux OS, the Apache HTTP Server, a MySQL relational DBMS (like MariaDB), and PHP.

 - **Client Tier:** The application client which in this case is a web browser software that processes and displays HTML resources, issues HTTP requests for resources, and processes HTTP responses.

 - **Load Balancer:** Nginx is used for HTTP Load Balancing to distribute requests through multiple application servers.

## Shared Services
 - **Storage Filer:** A NAS (Network Attached Storage) filer is used to provide reliable and stable external storage for the application tier servers.
 - **SFTP Server:** SFTP, which stands for SSH File Transfer Protocol is used to transfer data amongst two remote systems.
 - **Backup Server:** A staging backup system used for short term archival.
 - **Jump Server:** The intermediary host or an SSH gateway to a remote network hosting the Nautilus application.

## Infrastructure Details

| **Server Name**            | **IP**   | **Hostname** | **User** | **Password** | **Purpose**                      |
|:---------------------------|:---------|:-------------|:---------|:-------------|:---------------------------------|
| Application Server 1       | Dynamic  | stapp01      | tony     | Ir0nM@n      | Hosts Nautilus Application 1     |
| Application Server 2       | Dynamic  | stapp02      | steve    | Am3ric@      | Hosts Nautilus Application 2     |
| Application Server 3       | Dynamic  | stapp03      | banner   | BigGr33n     | Hosts Nautilus Application 3     |
| LoadBalancer Server        | Dynamic  | stlb01       | loki     | Mischi3f     | Distributes traffic for Nautilus HTTP |
| Database Server            | Dynamic  | stdb01       | peter    | Sp!dy        | Hosts Nautilus Database          |
| Storage Server             | Dynamic  | ststor01     | natasha  | Bl@kW        | Stores data for Nautilus Servers |
| Backup Server              | Dynamic  | stbkp01      | clint    | H@wk3y3      | Manages backups for Nautilus Servers |
| Mail Server                | Dynamic  | stmail01     | groot    | Gr00T123     | Manages email services for Nautilus Servers |
| Jump Host Server           | Dynamic  | jump-host    | thor     | mjolnir123   | Provides secure access to Stork DC |
| Jenkins Server             | Dynamic  | jenkins      | jenkins  | j@rv!s       | Runs Jenkins for CI/CD pipeline  |
