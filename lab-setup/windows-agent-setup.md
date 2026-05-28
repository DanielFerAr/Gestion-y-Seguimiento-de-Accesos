# 🪟 Instalación del Agente Wazuh en Windows

Este documento describe cómo instalar y configurar el agente Wazuh en un endpoint Windows para monitorear accesos.

---

## 1. Descargar el agente
Desde el Dashboard:

**Menu → Agents → Deploy new agent → Windows**

Descargar el instalador `.msi`.

---

## 2. Instalar el agente
Ejecutar:

wazuh-agent-4.x.x.msi


Configurar:
- Dirección del Manager
- Puerto 1514/udp
- Puerto 1515/tcp

---

## 3. Iniciar el servicio
```powershell
net start wazuh
```
## 4. Verificar conexión
En el Dashboard:

```powershell
Agents → Status → Active
```
---

## 5. Instalar Sysmon
Sysmon se instala siguiendo el archivo `sysmon-setup.md.`

---

## Resultado
El endpoint Windows queda listo para enviar:
- Event Logs (4624, 4625, 4672, 4720, 4726, 4728)
- Sysmon logs
