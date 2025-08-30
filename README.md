
wget -q -O /usr/share/keyrings/grafana.key https://apt.grafana.com/gpg.key

apt install -y apt-transport-https

echo "deb [signed-by=/usr/share/keyrings/grafana.key] https://mirrors.tuna.tsinghua.edu.cn/grafana/apt/ stable main" >> /etc/apt/sources.list.d/grafana.list
