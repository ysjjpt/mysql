
wget -q -O /usr/share/keyrings/grafana.key https://apt.grafana.com/gpg.key

apt install -y apt-transport-https

echo "deb [signed-by=/usr/share/keyrings/grafana.key] https://mirrors.tuna.tsinghua.edu.cn/grafana/apt/ stable main" >> /etc/apt/sources.list.d/grafana.list
groups:
- name: mysql.rules
  rules:
  - alert: MySQLHighThreadsConnected
    expr: mysql_global_status_threads_connected > 1
    for: 1m
    labels:
      severity: warning
    annotations:
      summary: "MySQL连接数过高"
      description: "MySQL连接线程数大于1 (当前值: {{ $value }})"
