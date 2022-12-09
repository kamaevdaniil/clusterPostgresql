### Скачиваем репозиторий 
git clone https://github.com/zalando/patroni
### Заменяем файлы
  Dockerfile
  
  docker-compose.yml
## Three-node Patroni cluster with three-node etcd cluster and one haproxy container using docker-compose
Example:

    Собираем образ и запускаем контейнер
    
    docker compose up --build -d
    
    выводим запущенные сервисы
    
    docker ps -a
    
### Возможные проблемы
1. Сервисы demo-patroni отваливаются 

    скорее всего не удаётся сделать монтирование, проверте статус владелца монтируемых директорий на локальном хосте:
Example:
    ```
    ls -l
    sudo chown 999:999 patroni1 patroni2 patroni3
    ```
  ```
   drwx------ 19 systemd-coredump systemd-coredump 4096 дек  9 18:43 patroni1
   drwxrwxrwx 19 systemd-coredump systemd-coredump 4096 дек  9 18:53 patroni2
   drwxrwxrwx 19 systemd-coredump systemd-coredump 4096 дек  9 18:53 patroni3
   ```
  
   
  



    
    

