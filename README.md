# Storj Statistics Setup

https://storjstats.info

## Featurelist
* setup [Json Exporter](https://github.com/prometheus-community/json_exporter) Container per JSON File/Source
* setup [Victoria Metrics](https://github.com/VictoriaMetrics/VictoriaMetrics.github.io) Container
* setup Grafana Container
* setup [NGINX Proxy Manager](https://nginxproxymanager.com/) Container

With this Ansiblerole you can setup an Grafanafrontend, together with Victoria Metrics and some Exporters to scrape data from [stats.storjshare.io](https://stats.storjshare.io/).

## Requirements

The target server needs to have Docker already installed and running.

## Role Variables

|Variable|Description|Default value|Required|
| :- |:-| -:| -:|
|storj_stats_network_name|Name of Dockernetwork|storj|no|
|storj_stats_network_subnet|Subnet of Dockernetwork |172.11.0.0/24|no|
|storj_stats_network_gateway|Gateway of Dockernetwork | 172.11.0.1|no|
|storj_stats_network_iprange|Range of Dockernetwork | 172.11.0.64/26|no|
|storj_stats_deploy_proxy|Dploey the nginx Proxy manager?|True|no|
|storj_stats_exporter_config_template_path|Configtemplate for the Exporter|json_exporter|no|
|storj_stats_vm_config_template|Configtemplate for Victoria Metrics|victoriametrics/vm_jobs.yml.j2|no|
|storj_stats_vm_retention|Retention of Data which is stored in Victoria Metrics|120|no|
|storj_stats_grafana_provisioning_config_template_path|Provisioning Template Path|grafana|no|
|storj_stats_grafana_adminuser_name|Grafana Admin User|admin|no|
|storj_stats_grafana_adminuser_password|Grafana Admin Password|admin|no|

## Example Ansible files

inventory

```yml
[storj]
<hostname-storj-server>
```

storj-stats.yml

```yml
- hosts: storj
  roles:
    - { role: role-storj-stats}
```

Example ansible run

```bash
 ansible-playbook -i inventory storj-stats.yml
```
