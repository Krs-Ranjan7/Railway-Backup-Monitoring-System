Backup Monitoring System (BMS) — East Coast Railway

An enterprise-grade, centralized web platform designed for the East Coast Railway (ECoR) to automate, monitor, and manage database backup operations across distributed railway servers and data centers.

📌 Project Overview

In critical public infrastructures like Indian Railways, data integrity, high availability, and disaster recovery readiness are paramount. Traditional backup workflows often rely on fragmented manual scripts and unmonitored cron jobs, which can lead to human error, scheduling conflicts, and "silent failures" where backups fail without administrative notification.   The Backup Monitoring System (BMS) replaces legacy administrative workflows with a modernized, decoupled full-stack architecture. It acts as a secure middleware bridge between system administrators and remote database nodes, offering real-time status diagnostics, automated scheduling, and a comprehensive audit ledger.

🏗️ System Architecture & Technology Stack

The project follows a decoupled, multi-tier enterprise architecture:

Frontend Layer: React.js (Single Page Application, SPA) providing a dynamic, responsive dashboard.

Backend Controller & Service Layer: Spring Boot (Java 17) handling REST APIs, business logic, and multi-threaded background task scheduling.

Data Access Layer: Spring Data JPA / Hibernate.

Database & Tooling Layer:
MySQL Server: Stores internal application configurations, user credentials, and history logs.
Native mysqldump Engine: Programmatically invoked via host operating system execution threads to generate uncorrupted, standard structural database snapshots.   

📊 Key Features

Centralized Dashboard: A unified control panel providing global health statuses, IP tracking, and live connectivity badges for all registered database nodes.

Dynamic Instance Management: Easily register, update, or remove remote database instances by configuring network IPs, ports, and engine types.

Real-Time Connectivity Diagnostics: Instant TCP socket handshake tests to verify network reachability before initializing backup routines.

Automated & On-Demand Backups: Support for both time-driven background backup scheduling and instantaneous "Backup Now" manual execution.

Concurrency Guardrails: Enforces systemic protection locks to block conflicting or overlapping backup routines on the same database node.

Immutable Audit Trail: Automatically logs execution durations, file sizes, storage destination paths, and success/error remarks into a relational history ledger. 

🗄️ Database Schema Design

The internal database (ecor_bms_config) consists of four primary relational tables:

USERS: Manages administrator credentials (user_id, username, password_hash, email).

INSTANCES: Tracks remote database targets (instance_id, instance_name, db_type, ip_address, port_number, status).

BACKUP_SCHEDULE: Stores automated scheduling rules (schedule_id, instance_id, scheduled_time, backup_location, is_active).

BACKUP_HISTORY: Maintains an immutable log of past backup runs (history_id, instance_id, backup_date, backup_duration, file_size, remark).

🚀 Getting Started & Installation

PrerequisitesJava JDK 17 or higher

Node.js (v18+) & npm

MySQL Server 8.0+

Native mysqldump utility installed and registered in the host OS environment path.   

🔮 Future Enhancements

Cloud Object Storage Integration: Direct streaming of compressed backup files to cloud destinations (AWS S3, Azure Blob Storage).

Instant Alerting Relays: Automated email or messaging notifications (Telegram/WhatsApp) triggered instantly when a backup job fails.

Multi-DBMS Support: Extending backend abstraction layers to support PostgreSQL and Oracle databases alongside MySQL. 

👨‍🎓 Project Details

Project Type: Industry-Oriented Full-Stack Development Project

Domain: Enterprise IT Infrastructure, Database Administration, Automation

Organization: East Coast Railway (ECoR), Bhubaneswar
