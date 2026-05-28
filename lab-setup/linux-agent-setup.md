# 🐧 Instalación del Agente Wazuh en Linux

Este documento describe cómo instalar y configurar el agente Wazuh en Linux para monitorear accesos, sudo, SSH y cambios de usuarios.

---

## 1. Instalar dependencias
```Bash
sudo apt update
sudo apt install curl gnupg -y
```
---
## 2. Descargar e instalar el agente
```Bash
curl -s https://packages.wazuh.com/key/GPG-KEY-WAZUH | sudo apt-key add -
echo "deb https://packages.wazuh.com/4.x/apt/ stable main" | sudo tee /etc/apt/sources.list.d/wazuh.list
sudo apt update
sudo apt install wazuh-agent -y
```
---
## 3. Configurar el Manager
Editar: 
```Bash
sudo nano /var/ossec/etc/ossec.conf
```
Agregar:
```Xml
<server>
  <address>IP_DEL_MANAGER</address>
  <port>1514</port>
</server>
```
---
## 4. Iniciar el agente
```Bash
sudo systemctl enable wazuh-agent
sudo systemctl start wazuh-agent
```
---
## 5. Instalar auditd
```Bash
sudo apt install auditd audispd-plugins -y
```
Copiar el archivo `auditd.rules` del repositorio:
```Codigo
/etc/audit/rules.d/audit.rules
```
Reiniciar auditd:
```Bash
sudo systemctl restart auditd
```
---
## Resultado
El endpoint Linux queda listo para enviar:
- SSH logs
- sudo logs
- cambios en passwd, shadow, group
- actividad sospechosa
