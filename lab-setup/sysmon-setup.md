# ⚙️ Instalación de Sysmon en Windows

Sysmon permite registrar eventos avanzados de procesos, red y cambios críticos relacionados con accesos.

---

## 1. Descargar Sysmon
```powershell
Invoke-WebRequest -Uri https://download.sysinternals.com/files/Sysmon.zip -OutFile Sysmon.zip
Expand-Archive Sysmon.zip -DestinationPath Sysmon
```

---

## 2. Copiar la configuración del repositorio
Archivo:
```codigo
/wazuh/sysmon-config.xml
```

---

## 3. Instalar Sysmon con la configuración
```powershell
Sysmon.exe -accepteula -i sysmon-config.xml
```

---

## 4. Verificar instalación
```powershell
Get-Service Sysmon
```
Debe aparecer como **Running.**

---

## Resultado
Sysmon queda configurado para monitorear:
- RDP
- WinRM
- cambios de usuarios y grupos
- ejecución de herramientas administrativas
- actividad sospechosa
