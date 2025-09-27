Dockerized Node.js contact app on EC2 with MySQL RDS (AWS)
# Dockerized Node.js Contact App with MySQL RDS (AWS)

A demo project showing a Dockerized Node.js contact application running on an EC2 instance and using Amazon RDS (MySQL) for persistent storage.  
This repository contains architecture diagrams, screenshots, deployment steps and project documentation.

## Architecture
<img src="<img width="1536" height="1024" alt="Dockerized Node js contact app on EC2 with MySQL RDS (AWS))" src="https://github.com/user-attachments/assets/3b95387c-59a2-4376-88ef-163373853c65" />
" alt="Architecture diagram: User → EC2 (Docker) → RDS MySQL with snapshots" width="800"/>

**High level flow**:  
User (browser) → EC2 (Docker container running Node.js app) → Amazon RDS (MySQL). RDS snapshot used for backup.

## Screenshots
### App UI
![App UI]<img width="1920" height="1020" alt="screenshot-app-ui png" src="https://github.com/user-attachments/assets/67ea9a6f-e0f5-4022-9a94-5516b53eb734" />

*Description: Application add/show contacts page.*

### RDS Console
![RDS Console]<img width="1920" height="1020" alt="screenshot-rds-console png" src="https://github.com/user-attachments/assets/fef2dc44-bc5f-4586-8315-d0476780589c" />
![RDS Console],img width="900" height="1000" alt="<img width="1920" height="1020" alt="screenshot-rds-console png (3)" src="https://github.com/user-attachments/assets/af01c4f4-1a39-42a5-9fd9-400fd577d507" />


*Description: RDS instance details and snapshot list.*

### MySQL Query / Database
![MySQL Queries]<img width="1920" height="1020" alt="screenshot-mysql png" src="https://github.com/user-attachments/assets/68ee054f-7f23-4487-8749-9639d14ba479" />

*Description: DB tables & sample queries used to verify `my_app_db`.*

## Project docs
- Full project documentation: [docs/project-doc.pdf]()

## How to run (local / quick)
1. Clone repo: `git clone https://github.com/umarshaikh36/docker-nodejs-rds-aws.git`
2. `cd docker-nodejs-rds-aws`
3. Create `.env` using `.env.example` and set DB connection strings
4. Build & run Docker (example):
```bash
docker build -t contact-app .
docker run -e DB_HOST=<rds-endpoint> -e DB_USER=<user> -e DB_PASS=<pass> -p 80:3000 contact-app
