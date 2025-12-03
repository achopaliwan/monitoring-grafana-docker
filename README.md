# monitoring-grafana-docker

## 1️⃣ Folder Structure  
> project-root/  
> │  
> ├── docker-compose.yml  
> └── prometheus/  
>    └── prometheus.yml  

## 2️⃣ Updated docker-compose.yml  
Adjust the docker-compose.yml file  
  
## 3️⃣ Create Prometheus Configuration File  
Adjust the Prometheus config on prometheus/prometheus.yml folder  
  
4️⃣ Start docker-compose.yml  
From your project directory:  
> docker compose up -d  
  
Confirm all services are running:  
> docker ps  
  
You should se:  
prometheus  
grafana  
cadvisor  
node_exporter  
raptor_web  
falcon_web  
  
## 5️⃣ Access Dashboards  
| Service           | URL                                                            | Description                          |
| ----------------- | -------------------------------------------------------------- | ------------------------------------ |
| **Prometheus**    | [http://localhost:9090](http://localhost:9090)                 | raw metrics explorer                 |
| **cAdvisor**      | [http://localhost:8083](http://localhost:8083)                 | container performance view           |
| **Node Exporter** | [http://localhost:9100/metrics](http://localhost:9100/metrics) | Linux host metrics                   |
| **Grafana**       | [http://localhost:3000](http://localhost:3000)                 | dashboards (login: admin / admin123) |
  
## 6️⃣ Configure Grafana  
Login to Grafana [http://localhost:3000](http://localhost:3000) :  
  
Go to ⚙️ → Data Sources → Add data source  
Choose Prometheus  
Set URL: http://prometheus:9090  
Click Save & Test  
  
Then:  
Import Dashboard ID 893 (Node Exporter Full)  
Import Dashboard ID 13946 or 1860  (Docker & cAdvisor metrics)  
  
Docker and system monitoring :  
<img width="1913" height="961" alt="image" src="https://github.com/user-attachments/assets/530e7f01-203b-4688-8cf9-ff901514d9ee" />  
  
Docker-cAdvisor :  
<img width="1918" height="951" alt="image" src="https://github.com/user-attachments/assets/f5cb8a51-a683-4f03-be39-7fb4530461e4" />  
