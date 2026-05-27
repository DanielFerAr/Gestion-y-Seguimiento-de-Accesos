# Gestion-y-Seguimiento-de-Accesos
El objetivo del siguiente proyecto es centralizar, monitorear y detectar eventos críticos de autenticación, cambios de permisos y elevación de privilegios, aplicando principios de mínimo privilegio y control de accesos. Incluye reglas personalizadas en Wazuh, casos de prueba reproducibles y dashboards orientados a visibilidad de accesos.
### 1. Gestión de usuarios y permisos
Implica administrar:
- Cuentas de usuario
- Roles y grupos
- Permisos sobre recursos
- Accesos administrativos

Un SOC no administra permisos, pero sí monitorea:
- Quién accede
- Desde dónde
- Con qué permisos
- Qué acciones realiza

### 2. Ciclo de vida de accesos (Alta – Baja – Modificación)
**Alta:** creación de cuentas y asignación de permisos mínimos.  
**Baja:** deshabilitación o eliminación de accesos.  
**Modificación:** cambios de roles, grupos o privilegios.

El SOC debe detectar:
- Creación o eliminación de cuentas
- Cambios en grupos privilegiados
- Elevación de privilegios inesperada
- Actividad de cuentas deshabilitadas

### 3. Principio de mínimo privilegio (PoLP)
Cada usuario debe tener únicamente los permisos necesarios para su función.  
El SOC monitorea:
- Uso de privilegios elevados
- Accesos administrativos fuera de horario
- Comandos ejecutados con sudo
- Accesos remotos sospechosos

### 4. Control de accesos (AAA)
- **Autenticación:** verificar identidad  
- **Autorización:** validar permisos  
- **Auditoría:** registrar y monitorear actividad  

Este laboratorio se enfoca en la **auditoría**, correlación y detección de eventos de acceso.
