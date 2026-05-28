# 🔐 Home SOC Lab – Gestión y Seguimiento de Accesos

Este proyecto implementa un laboratorio SOC enfocado en la **gestión y seguimiento de accesos** en sistemas Windows y Linux. Su objetivo es centralizar, monitorear y detectar eventos críticos de autenticación, cambios de permisos y elevación de privilegios, aplicando principios de mínimo privilegio y control de accesos. Incluye reglas personalizadas en Wazuh, casos de prueba reproducibles, incidentes simulados y dashboards orientados a visibilidad de accesos.

---

# 🧩 1. Conceptos Clave de Gestión de Accesos

La gestión de accesos es un componente esencial de la seguridad organizacional y un área crítica para el monitoreo dentro de un SOC. Este laboratorio se enfoca en comprender, auditar y detectar eventos relacionados con accesos válidos, inválidos y sospechosos en sistemas Windows y Linux.

### 🔸 Gestión de usuarios y permisos
Un SOC monitorea:
- Quién accede  
- Desde dónde  
- Con qué permisos  
- Qué acciones realiza  

### 🔸 Ciclo de vida de accesos (Alta – Baja – Modificación)
El SOC debe detectar:
- Creación o eliminación de cuentas  
- Cambios en grupos privilegiados  
- Elevación de privilegios inesperada  
- Actividad de cuentas deshabilitadas  

### 🔸 Principio de mínimo privilegio (PoLP)
Monitoreo de:
- Uso de privilegios elevados  
- Accesos administrativos fuera de horario  
- Comandos ejecutados con sudo  
- Accesos remotos sospechosos  

### 🔸 Control de accesos (AAA)
Este laboratorio se enfoca en la **auditoría**, correlación y detección de eventos de acceso.

---

# 🏗️ 2. Arquitectura del Laboratorio

La arquitectura completa se encuentra en:

📄 `/architecture/architecture.md`  
📄 `/architecture/components.md`  
📄 `/architecture/architecture-diagram.mmd`  
📄 `/architecture/data-flow.mmd`

### Resumen visual

Windows/Linux → Wazuh Agent → Wazuh Manager → Wazuh Indexer → Dashboard


---

# 🛡️ 3. Reglas Wazuh Personalizadas

Las reglas completas se encuentran en:

📄 `/wazuh/local_rules.xml`

Incluyen detecciones para:
- Creación/eliminación de usuarios  
- Cambios en grupos privilegiados  
- Uso de sudo  
- SSH fallido/exitoso  
- Fuerza bruta  
- Logins remotos  
- Actividad de cuentas deshabilitadas  
- Privilege escalation  

Ejemplo incluido en el README:

```xml
<rule id="300101" level="7">
  <field name="win.system.eventID">4726</field>
  <description>Windows: Eliminación de una cuenta de usuario</description>
</rule>
```

---

# 🛡️ 4. Casos de Uso (Use Cases)

Los casos de uso completos están en:

📄 `/use-cases/windows-access-cases.md ` 
📄 `/use-cases/linux-access-cases.md ` 
📄 `/use-cases/ad-access-cases.md `

Incluyen:
- SSH fallido/exitoso
- Fuerza bruta SSH
- Login fallido Windows
- Login remoto RDP
- Creación/eliminación de usuarios
- Cambios en grupos privilegiados
- Uso de sudo

---

# 🚨 5. Incidentes Simulados

Los incidentes completos están en:

📄 `/incidents/brute-force-windows.md ` 
📄 `/incidents/brute-force-ssh.md `
📄 `/incidents/privilege-escalation.md ` 
📄 `/incidents/remote-login.md `
 
Incluyen:
- Evidencia
- Logs
- Reglas activadas
- Análisis SOC
- Acciones recomendadas

---

# 🏗️ 6. Setup del Laboratorio
Toda la configuración está en:

📄 `/lab-setup/wazuh-install.md `  
📄 `/lab-setup/windows-agent-setup.md ` 
📄 `/lab-setup/linux-agent-setup.md `  
📄 `/lab-setup/sysmon-setup.md `

Incluye:
- Instalación del stack Wazuh
- Instalación de agentes Windows y Linux
- Configuración de auditd
- Instalación de Sysmon con config optimizada


# 📁 7. Estructura Final del Repositorio
```codigo
home-access-monitoring-lab/
│
├── architecture/
├── wazuh/
├── use-cases/
├── incidents/
├── lab-setup/
└── README.md
```

---

# 👤 Autor
**Daniel – Ingeniero orientado a SOC**
Proyecto diseñado para demostrar habilidades prácticas en monitoreo, detección y análisis de accesos.
