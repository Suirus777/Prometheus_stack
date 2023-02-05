<h2> Задание C2.7 </h2>
<br>
1. Разверните Prometheus Stack через docker-compose, в котором будет:<br>
<br>
* Prometheus;<br>
* Grafana;<br>
* Node Exporter;<br>
* Blackbox Exporter;<br>
* AlertManager.<br><br>
<b> Ответ: был развёрнут полный Prometheus Stack через docker-compose: <br>
<br>
root@grafana:/home/user/grafana# docker ps <br>
CONTAINER ID        IMAGE                       COMMAND                  CREATED             STATUS              PORTS                      NAMES <br>
550ddd67e1c3        prom/alertmanager:v0.23.0   "/bin/alertmanager -…"   17 hours ago        Up 8 hours          0.0.0.0:9093->9093/tcp     grafana_alertmanager_1 <br>
3c0a13864bdb        prom/blackbox-exporter      "/bin/blackbox_expor…"   18 hours ago        Up 8 hours          127.0.0.1:9115->9115/tcp   grafana_blackbox-exporter_1 <br>
47095dad3733        prom/node-exporter          "/bin/node_exporter …"   19 hours ago        Up 8 hours          0.0.0.0:9100->9100/tcp     grafana_node-exporter_1 <br> 
3cdbed1b9cd4        grafana/grafana             "/run.sh"                19 hours ago        Up 8 hours          0.0.0.0:3000->3000/tcp     grafana_grafana_1 <br>
f86812f2adf7        prom/prometheus:latest      "/bin/prometheus --c…"   21 hours ago        Up 2 seconds        0.0.0.0:9090->9090/tcp     grafana_prometheus_1 <br>
</b><br>

2. Соберите метрики с https://lms.skillfactory.ru через Blackbox, соберите метрики с вашего сервера через Node Exporter.<br>
<br>
<b> Ответ: Было сделано, собраны метрики с https://lms.skillfactory.ru через Blackbox
</b><br><br>

3. Создайте dashboard в Grafana, в котором будут отображены следующие метрики:<br>
<br>

На вашем сервере (или локальной машине):<br>
<br>
* время работы (Uptime);<br>
* нагрузка на процессор (CPU) в %;<br>
* использование памяти (RAM) в %;<br>
* использование диска в %.<br>
<br>
На lms.skillfactory.ru:<br>
<br>
* возвращаемый статус-код;<br>
* задержка ответа сайта;<br>
* срок действия сертификата.<br>
<br>

4. Добавьте алерты в AlertManager на следующие события:<br>
<br>
* изменился статус-код сайта lms.skillfactory.ru;<br>
* задержка превышает 5 секунд lms.skillfactory.ru;<br>
* сервер перезагрузился (через метрику Uptime).<br>

<b> Ответ: Было сделано, alerts можно увидеть в Github: prometheus/alert.yml <br>
Также будут отправлены скриншоты
</b><br><br>

В Телеграм алерты можно не отправлять. Если есть желание, в качестве дополнительного задания можно кидать их себе на почту.<br>
<br>
<b> Ответ: Была настроена отправка сообщений по почте настройки можно будет посмотреть в github: alertmanager/alertmanager.yml <br>
почтовые сообщения о состоянии метрик будут отправлены скриншотами
</b><br><br>

Оформите решение в виде скриншотов дашборда, скриншотов интерфейса AlertManager и конфигов используемых сервисов.<br>
<br>
<b> Сделано </b><br>
