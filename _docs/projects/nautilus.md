---
title: Nautilus
description: NAVAL Systems
---

##### xFusionCorp
123 Marvis Bay
Syldavia

# Project Nautilus

## OVERVIEW
Project Nautilus is the Naval subdivision of the xFusionCorp Industries.
Nautilus Application helps the Naval forces to make smart procurement decisions of their manned or unmanned maritime systems while ensuring that the operational requirements are met. It also aims to provide the best in class operational support, improving the safety and life extension of existing machines and reduction in the cost of ownership.

## Current Repertoire:
1. Sonar Technology and Systems
2. LUSV - Large Unmanned Surface Vehicles
3. Autonomous Unmanned Undersea Pods
4. Nuclear Submarines
5. Laser Guidance Systems

## Application Architecture:
Nautilus Deployment Architecture can be viewed [here](https://www.lucidchart.com/documents/edit/58e22de2-c446-4b49-ae0f-db79a3318e97/0_0?shared=true)

The Nautilus is a three-tier application and is deployed in the Stratos Datacenter in the North American Region.

 - **Data Tier:** The Data tier is the layer that stores data with the retrieval storage and execution methods made by the application layer. We are making use of MariaDB which is one of the most popular open source relational databases.

 - **Application Tier:** Makes use of a LAMP which is a stack of open-source software that can be used to create web applications. LAMP is an acronym that usually consists of the Linux OS, the Apache HTTP Server, a MySQL relational DBMS (like MariaDB), and PHP.

 - **Client Tier:** The application client which in this case is a web browser software that processes and displays HTML resources, issues HTTP requests for resources, and processes HTTP responses.

 - **Load Balancer:** Nginx is used for HTTP Load Balancing to distribute requests through multiple application servers.

## Shared Services:
 - **Storage Filer:** A NAS (Network Attached Storage) filer is used to provide reliable and stable external storage for the application tier servers.
 - **SFTP Server:** SFTP, which stands for SSH File Transfer Protocol is used to transfer data amongst two remote systems.
 - **Backup Server:** A staging backup system used for short term archival.
 - **Jump Server:** The intermediary host or an SSH gateway to a remote network hosting the Nautilus application.

## Infrastructure Details:

| **Server Name** | **IP**|**Hostname** | **User** |**Password**|**Purpose** |
|:---            |:---    |:---      |:--          |:---        |:---
|stapp01         | 172.16.238.10 | stapp01.stratos.xfusioncorp.com |tony | Ir0nM@n |Nautilus App 1
|stapp02         | 172.16.238.11 | stapp02.stratos.xfusioncorp.com |steve | Am3ric@ |Nautilus App 2
|stapp03         | 172.16.238.12 | stapp03.stratos.xfusioncorp.com | banner | BigGr33n |Nautilus App 3
|stlb01          | 172.16.238.14 | stlb01.stratos.xfusioncorp.com |loki | Mischi3f |Nautilus HTTP LBR
|stdb01          | 172.16.239.10 | stdb01.stratos.xfusioncorp.com |peter | Sp!dy |Nautilus DB Server
|ststor01        |172.16.238.15  | ststor01.stratos.xfusioncorp.com |natasha | Bl@kW |Stork DC Storage Filer
|stbkp01         | 172.16.238.16 | stbkp01.stratos.xfusioncorp.com |clint |H@wk3y3  | Nautilus Backup Server
|stmail01        | 172.16.238.17 | stmail01.stratos.xfusioncorp.com |groot |Gr00T123  | Nautilus Mail Server
|jump_host       | Dynamic       | jump_host.stratos.xfusioncorp.com |thor|mjolnir123 |Jump Server to Access Stork DC
 
