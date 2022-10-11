# Выполнено ДЗ №1

- [ ] Основное ДЗ
- [ ] Задание со *

## В процессе сделано:
- Разобрался почему все pod в namespace kube-system восстановились после удаления
Поды etcd-minikube, kube-apiserver-minikube, kube-controller-manager-minikube, kube-scheduler-minikube являются static pods и управляются kubelet на определенных нодах. Манифесты лежат /etc/kubernetes/manifests и перезапускаются они в случае сбоя или удаления по этим манифестам с помощью kubelet.
Как я понял эти правила перезапуска зашиты записаны в этих манифестах. Посмотреть их можно зайдя в minikube ssh.
Поды core-dns и kube-proxy поднимаются из манифестов которые лежат в etcd и соответственно поднимаются после etcd
- Создал Dockerfile, создал образ на базе nginx
- Создал манифест пода web, поднял под в котором 2 контейнера - основной и init и сделал между ними volume чтобы index.html попал в основной контейнер - и после подключения volume то содержимое папки которое я добавлял (homework.html) пропало, ну потому что теперь мы ссылаемся на volume. Как сделать так чтобы и volume был и то что лежало в app сохранилось ???
Проверил работоспособность, получил index.html.
- Склонировал frontend HipsterShop https://github.com/GoogleCloudPlatform/microservices-demo/tree/main/src/frontend 
- Создал образ на базе nginx (за основу взял Dockerfile для web)
- Выполнил задание со *