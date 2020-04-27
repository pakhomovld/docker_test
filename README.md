# docker_test

Для развертывания среды необходимо:
  1. Склонировать репозиторий 
  2. В директории проекта выполнить команду docker-compose up -d --build
  3. Среда развернута и доступна по адресу http://localhost:8000

Настройка xDebug:
  1. Preferences | Languages & Frameworks | PHP | Debug
  2. Xdebug port - 9000 - Apply
  3. Validate - Path to create validation script: /path_to_project/www/html/
  4. Url to validation script: http://localhost:8000
  5. Validate
