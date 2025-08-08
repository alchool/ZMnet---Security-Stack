# ZMnet---Security-Stack
 ecosistema open‑source integrato per: discovery asset, surface assessment, vulnerability scanning, patch management, central logging e orchestrazione di rimedio automatico.

# Diagramma

[Internet] --> [Shodan/API]         
                 |                  
        [Amass / Recon-ng / SpiderFoot] --> [Asset DB]
                 |                                |
                 v                                v
            [Nmap / ZAP / OpenVAS] --------------> [Logstash] --> [Elasticsearch/OpenSearch] --> [Kibana]
                 |                                ^                                    |
                 |                                |                                    v
[Endpoints] --> [Wazuh Agent / osquery] -----------+------------------------------> [Wazuh Manager]
                                                           |                             |
                                                           v                             v
                                                        [TheHive] <---> [Cortex]      [MISP]
                                                           |                             |
                                                           v                             v
                                                       [GLPI/OCS]  <---Webhook---  [Ansible Playbooks]
