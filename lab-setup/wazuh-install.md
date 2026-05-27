# 🏗️ Instalación del Wazuh Manager + Indexer + Dashboard

Este documento describe la instalación del stack completo de Wazuh para el laboratorio de Gestión y Seguimiento de Accesos.

---

## 📌 Requisitos
- Ubuntu Server 22.04
- 4 GB RAM mínimo
- 2 vCPU
- 20 GB de disco

---

## 1. Actualizar el sistema
```bash
sudo apt update && sudo apt upgrade -y

---

## 2. Descargar e instalar el agente
```bash
curl -s https://packages.wazuh.com/key/GPG-KEY-WAZUH | sudo apt-key add -
echo "deb https://packages.wazuh.com/4.x/apt/ stable main" | sudo tee /etc/apt/sources.list.d/wazuh.list
sudo apt update
sudo apt install wazuh-agent -y

---
