# hw2

Как запустить сервис:
1) скачать репозиторий
2) перейти в корень репоитория
3) применить конфигурации командой `kubectl apply -f app-config.yaml -f postgres.yaml -f initdb.yaml -f deployment.yaml -f service.yaml -f ingress.yaml`
4) прописать домен arch.homework в локальный файл /etc/hosts командой `echo "$(minikube ip) arch.homework" | sudo tee -a /etc/hosts`

Проверить работоспособность `curl -i http://arch.homework/health/`

Получим ответ от сервиса `'{"status": "ok"}'`

Проверить работоспособность `curl -i http://arch.homework/user/1`

Получим ответ от сервиса `{"id":1,"name":"Spasateli","phone":"101"}` - это пользователь добавленный init миграцией

В репозитории содержатся файл postman коллекции HW2.postman_collection.json с тестовыми запросами на добавление / модификацию / чтение / удаление 
