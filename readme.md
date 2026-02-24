Тестовое задание для Effective Mobile по разворачиванию простого веб-приложения
Используемые технологии: Python (HTTP Backend), nginx (reverse proxy), Docker - разворачивание через контейнеры (используется compose)

---------------
 - Backend работает на Python, слушает порт 8080
 - Backend недоступен за пределами Docker-сети
 - nginx запускается только при healthy-статусе backend
 - nginx слушает 80 порт и проксирует запрос на backend
---------------
**Для запуска:**
Склонировать репозиторий   
Запустить при помощи:   

```
docker compose up -d --build
```
---------------
** Для проверки: **   
Проверка логов запуска:   

```
docker compose logs
```
Проверка работоспособности:   
```
curl http://localhost
```
Ожидаемый ответ:   
**"Hello from Effective Mobile!"**

Краткая схема:   
[ Client ]   
     |           
     v          
[ Nginx :80 ]    
     |         
     v         
[ Backend :8080 ]
