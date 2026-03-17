University: ITMO University  
Faculty: [FTMI]  
Course: Введение в веб технологии  
Year: 2025/2026  
Group: U4125  
Author: Nazarova Arina Ilinichna  
Lab: Lab2  
Date of create: 16.03.2026  
Date of finished: 16.03.2026  

**Ход работы:**  
1. Создала файлы app.py, requirements.txt, Dockerfile и с помощью команды nano заполнила заданными условиями.
   <img width="453" height="45" alt="MacBook-Pro docker-ci-cd-lab arexava$ nano requirements txt" src="https://github.com/user-attachments/assets/6950db01-1b71-4ea6-b92a-da1d140c4009" />
   
2. Создала Docker образ и запустила контейнер.
   <img width="789" height="371" alt="Снимок экрана 2026-03-17 в 00 05 28" src="https://github.com/user-attachments/assets/260ef487-b7ef-4e55-bbaf-1f1917b4fb36" />
   
*в лабе указан порт 5000, я использовала 5001, поскольку 5000 занят системой и при попытке задать команду выдавалась ошибка.  

<img width="789" height="71" alt="Снимок экрана 2026-03-17 в 00 06 36" src="https://github.com/user-attachments/assets/114ea303-9a2e-46b4-86dd-bee88dfc3920" />  

<img width="729" height="30" alt="Снимок экрана 2026-03-17 в 00 04 42" src="https://github.com/user-attachments/assets/78eb6382-27ad-4b2c-836f-9377ed05d52f" />  


3. Проверила, что приложение работает:
   <img width="742" height="249" alt="Py" src="https://github.com/user-attachments/assets/7e25fabc-7e20-4a1b-b586-8d707f0ad953" />  

4. В репозитории была создана папка .github/workflows/, в которой размещен файл docker-build.yml с настроенным пайплайном, пайплайн выполняет следующие действия:  
- запускается при push в ветку main  
- выполняет checkout кода  
- настраивает Docker Buildx  
- выполняет авторизацию в Docker Hub  
- собирает Docker-образ  
- публикует образ в Docker Hub

5.В настройках GitHub репозитория были добавлены секреты:  
- DOCKER_USERNAME  
- DOCKER_PASSWORD
  <img width="651" height="203" alt="Снимок экрана 2026-03-17 в 19 35 51" src="https://github.com/user-attachments/assets/196bd365-3e7a-4fac-a41f-1be2157722e4" />

6. После внесения был выполнен push в репозиторий, сначала возникали ошибки, но после их устранения (в качестве пароля использовала новый токен доступа) процесс прошел успешно.  
<img width="596" height="93" alt="Снимок экрана 2026-03-17 в 19 37 30" src="https://github.com/user-attachments/assets/0bff90d0-00af-42b7-ae21-e238d1ad9b4b" />

7. В результате работы был настроен CI/CD пайплайн, который автоматически собирает и публикует Docker-образ при изменении кода.







   






