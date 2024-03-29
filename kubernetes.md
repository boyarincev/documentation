# Kubernetes

### Документация

{% embed url="https://kubernetes.io/ru/docs/reference/kubectl/cheatsheet" %}

{% embed url="https://kubernetes.io/ru/docs/reference/kubectl/overview" %}

### kubeconfig

1. опции `--kubeconfig` и пути к файлу
2. переменной окружения `$KUBECONFIG`
3. и файлу по-умолчанию – `$HOME/.kube/config`

{% embed url="https://rtfm.co.ua/kubernetes-kubectl-i-kubeconfig-obzor-fajla-dobavlenie-klastera-polzovatelya-i-konteksta" %}

### **Шпаргалка**

1. Если интересно, то мой флоу по работе с кубом: 1) я запускаю tmux, потому что в нем удобнее всего делить экран терминала на несколько частей 2) я делю на два экрана, как минимум 2.1)&#x20;

```
watch -n.2 kubectl -n oms-stage get all,ingress,deploy,secret 
```

\- команда показывает интерактивное состояние 2.2) и на втором экране я уже детально смотрю что происходит, например&#x20;

```
kubectl -n oms-stage logs -f pod/backend-oms-backend-6f8b48c647-nkwkk
```

#### Разное

```
//Доступные неймспейсы
kubectl get ns
// Информация о контейнерах
kubectl -n oms-stage get all,ingress,deploy
// Логи
kubectl -n oms-stage logs pod/taskmanager-6cf5bd466f-sjhrj
//Переменные окружения в контейнере
kubectl -n oms-stage exec -it pod/backend-oms-backend-79ccc46b55-8fwsl env
//Расширенная информация по контейнеру
kubectl describe pod/backend-oms-backend-955744bfb-h2bqj
//Посмотреть конфигмапы
kubectl  -n oms-stage get cm
//Посмотреть конкретную конфигмапу
kubectl  -n oms-stage get cm backend-env -o yaml
//Использованные ресурсы
kubectl -n oms-stage top pod
```

### Helm

Использует конфиг для kubectl

```
//Посмотреть релизы
helm -n oms list
//Удалить деплой
helm -n oms delete backend
```

Лучше сразу себе скачай helm и положи рядом с kubectl, чтобы был на всякий случай

Да и просто чтобы релизы смотреть

```
helm -n oms list
NAME            NAMESPACE       REVISION        UPDATED                                 STATUS          CHART                   APP VERSION
backend         oms             2               2022-03-24 05:59:08.46013567 +0000 UTC  failed          oms-backend-0.1.0       1.16.0     
frontend        oms             1               2022-03-25 14:42:08.496467197 +0000 UTC deployed        oms-front-0.0.1         1.16.0   
```

[https://github.com/EvgeniyBlinov/bash\_modules/blob/master/kubectl.sh](https://github.com/EvgeniyBlinov/bash\_modules/blob/master/kubectl.sh) - я вот такой скриптик юзаю для bash. Который переключает переменные окружения для kubectl
