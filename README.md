# Предварительные требования

```shell
git clone https://github.com/linkedin/oncall.git
```
```shell
cd oncall
```
```shell
eval $(minikube docker-env)
```
Используется windows, поэтому выполним
```shell
minikube -p minikube docker-env | Invoke-Expression
```
```shell
docker build -t oncall:latest
```
Создаём Secret с паролем к БД и Headless Service:
# MySQL
cd mysql
```shell
kubectl apply -f secret.yaml
```
![img.png](img.png)
```shell
kubectl apply -f service.yaml
```
![img_1.png](img_1.png)
Запускаем нагрузку MySQL
```shell
kubectl apply -f statefulset.yaml
```
![img_2.png](img_2.png)

Проверяем, запущен ли под:
```shell
kubectl get pod
```
![img_3.png](img_3.png)

#  2. Запуск OnCall
```shell
kubectl apply -f config.yaml

```
![img_4.png](img_4.png)
```shell
kubectl apply -f service.yaml
```
![img_6.png](img_6.png)
```shell
kubectl apply -f deployment.yaml
```
![img_7.png](img_7.png)
Проверяем, запущены ли поды
```shell
kubectl get pod
```
![img_8.png](img_8.png)
ошибку исправить не получается. К сожалению, поздно сел за ДЗ и не успеваю спросить решения в чате.