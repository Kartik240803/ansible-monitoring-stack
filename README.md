# ansible-monitoring-stack

Ansible playbook that provisions a full monitoring and security stack on Ubuntu/Debian servers in one run.

## What it installs

- **Grafana** (from the official APT repo)
- **Prometheus** with **Node Exporter** and **Blackbox Exporter** scrape config
- **Wazuh Dashboard** with TLS certificates and hardened file permissions
- Config templates for **Zabbix Server**, **Filebeat**, **OpenSearch Dashboards** and **InfluxDB**

## Usage

1. Add your hosts under a `Servers` group in your inventory
2. Set `target_username` for the remote user
3. Place the `.j2` templates in `/etc/ansible/config_files/`
4. Run: `ansible-playbook -i inventory site.yml`

All services are installed as systemd units and enabled on boot.
