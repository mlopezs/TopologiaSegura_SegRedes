# Topología Segura
Diseño e implementación de una topología de red segura para la asignatura de Seguridad en Redes.

En **Enunciado.pdf** podemos encontrar los requisitos para la realización de este ejercicio.

#### Archivos:
 - **Vagrantfile**: Fichero para la descripción de las máquinas virtuales, y que nos permite la construcción de las mismas. 
 - **playbook-servdmz.yml, playbook-pcmz.yml, playbook-router.yml**: Archivos para el aprovisionamiento de las máquinas con Ansible.
 - **iptables-rules**: Reglas de iptables que se aplican en el router.
 - **templates/dnsmasq.conf**: Archivo de configuración para dnsmasq.
 - **templates/dnsmasq-hosts**: Archivo de *hosts* para dnsmasq.
