SMEV-proxy, предоствляющий возможность сбора статистики по успешным и неуспешным запросам. 
Запросы проксируются со SMEV Transport Adapter (k8s) на соответствующий SMEV Endpoint.
Реализован с помощью :
1) Nginx c использованием ngx_http_stub_status_module для сбора базовых метрик о состоянии сервера,
   больше узнать о них можно по данной ссылке: 
https://nginx.org/ru/docs/http/ngx_http_stub_status_module.html
2) Nginx Prometheus Exporter для скрейпинга метрик c модуля и их преобразования в TSDB формат.

Дополнительная информация:
Деплой происходил через Helm. 
Планируется возможное тестирование механизма VPA на данном сервисе для решения общей проблемы с requests и limits в public контуре.
