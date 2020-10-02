# Ansible Role: ansible-apps_proxmox_exporter

## Description

[![Build Status](https://travis-ci.com/lotusnoir/ansible-apps_proxmox_exporter.svg?branch=master)](https://travis-ci.com/lotusnoir/ansible-apps_proxmox_exporter)[![License](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg)](https://opensource.org/licenses/MIT)[![Ansible Role](https://img.shields.io/badge/ansible%20role-apps__proxmox_exporter-blue)](https://galaxy.ansible.com/lotusnoir/ansible-apps_proxmox_exporter/)[![GitHub tag](https://img.shields.io/badge/version-latest-blue)](https://github.com/lotusnoir/ansible-apps_proxmox_exporter/tags)

Deploy [proxmox_exporter](https://github.com/boynux/proxmox-exporter) to expose proxmox metrics to prometheus.

## Role variables

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `proxmox_exporter_version` | 1.2.0 | proxmox_exporter version |
| `proxmox_exporter_install_dir` |  /etc/proxmox_exporter/| config directory |
| `proxmox_exporter_user` | pve_exporter@pve | proxmox user |
| `proxmox_exporter_password` | "" | password for proxmox user |
| `proxmox_exporter_listen_port` | 9111 | proxmox_exporter listen port |
| `proxmox_exporter_listen_address` | 127.0.0.1 | proxmox_exporter listen address |

## Examples

	---
	- hosts: apps_proxmox_exporter
	  become: yes
	  become_method: sudo
	  gather_facts: yes
	  roles:
	    - role: ansible-apps_proxmox_exporter
	  environment: 
	    http_proxy: "{{ http_proxy }}"
	    https_proxy: "{{ https_proxy }}"
	    no_proxy: "{{ no_proxy }}

## License

This project is licensed under MIT License. See [LICENSE](/LICENSE) for more details.
