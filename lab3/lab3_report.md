University: ITMO University  
Faculty: [FTMI]  
Course: Введение в веб технологии  
Year: 2025/2026  
Group: U4125  
Author: Nazarova Arina Ilinichna  
Lab: Lab3  
Date of create: 16.03.2026  
Date of finished: 16.03.2026  

**Ход работы:**  
1. Создание конфигурации Prometheus:
  Соpдала папку prometheus для конфигурации и файл prometheus/prometheus.yml  
<img width="551" height="33" alt="Снимок экрана 2026-03-17 в 19 46 22" src="https://github.com/user-attachments/assets/188371da-3382-4c94-957c-2d7e117e6c47" />

2. Запустила контейнер Node Exporter для сбора системных метрик с помощью команды docker run -d \ и проверила работу: curl http://localhost:9100/metrics  
<img width="563" height="295" alt="Снимок экрана 2026-03-17 в 19 56 07" src="https://github.com/user-attachments/assets/acfd8639-e870-49eb-9030-d324c5cd3360" />

3. Создала том для данных Prometheus (docker volume create prometheus-data) и создала общую сеть (docker network create monitoring)
   Вышла на папку выше консоли, убедилась, что нахожусь над уровнем папки prometheus. Запустила контейнер Prometheus: docker run -d \

4. Проверила работу: открыла http://localhost:9090 в браузере  
<img width="925" height="539" alt="Снимок экрана 2026-03-17 в 20 00 17" src="https://github.com/user-attachments/assets/223deb85-574b-4794-9106-73bc70dc650c" />

5.Запустила Grafana:  
  Создала том для данных Grafana: docker volume create grafana-data  
Запустила контейнер Grafana:  
  Проверила работу: http://localhost:3000 в браузере  
  Настроила Grafana:  
Вошла в Grafana, добавила источник данных Prometheus:  
  Configuration → Data Sources → Add data source  
Выбрала Prometheus  
URL: http://prometheus:9090  
Save & Test  
Создала дашборд:  
Create → Dashboard → Add visualization  
Выбрала источник данных Prometheus    
Добавила метрику: node_cpu_seconds_total  
Сохранила дашборд  
<img width="587" height="717" alt="Снимок экрана 2026-03-17 в 20 03 24" src="https://github.com/user-attachments/assets/ad742c3d-73d7-42f4-824a-5f412fe5a181" />  

Дашборд с треями метриками (node_cpu_seconds_total, node_memory_MemAvailable_bytes,node_memory_MemAvailable_bytes):  
<img width="707" height="772" alt="Снимок экрана 2026-03-17 в 20 11 32" src="https://github.com/user-attachments/assets/85801fd9-23d0-4915-ad35-e52a033efdb0" />



