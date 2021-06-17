# Storj Statistics Setup

https://storjstats.info

## Featurelist
* setup [Json Exporter](https://github.com/prometheus-community/json_exporter) Container per JSON File/Source
* setup Prometheus Container
* setup Grafana Container
* setup [NGINX Proxy Manager](https://nginxproxymanager.com/) Container

With this Ansiblerole you can setup an Grafanafrontend, together with Prometheus and some Exporters to scrape data from [stats.storjshare.io](https://stats.storjshare.io/).

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
|storj_stats_prometheus_config_template|Configtemplate for Prometheus|prometheus/prometheus.yml.j2|no|
|storj_stats_prometheus_retention|Retention of Data which is stored in Prometheus|10y|no|
|storj_stats_grafana_provisioning_config_template_path|Provisioning Template Path|grafana|no|
|storj_stats_grafana_adminuser_name|Grafana Admin User|admin|no|
|storj_stats_grafana_adminuser_password|Grafana Admin Password|admin|no|

## Dependencies

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

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
