# 🧩 Componentes del Laboratorio

## 1. Windows Endpoint
- Sysmon configurado para:
  - Logons remotos
  - Cambios de usuarios y grupos
  - Ejecución de herramientas administrativas
- Event Logs relevantes:
  - 4624 (login exitoso)
  - 4625 (login fallido)
  - 4672 (privilegios especiales)
  - 4720/4726 (alta/baja de usuarios)
  - 4728 (agregado a grupo privilegiado)

## 2. Linux Endpoint
- auditd monitoreando:
  - Cambios en passwd, shadow, group
  - SSH fallido/exitoso
  - Uso de sudo
  - Acceso a archivos sensibles
- auth.log para autenticación

## 3. Wazuh Manager
- Reglas personalizadas:
  - Fuerza bruta
  - Elevación de privilegios
  - Cambios de permisos
  - Accesos remotos
  - Actividad de cuentas deshabilitadas

## 4. Wazuh Indexer
- Almacena eventos normalizados
- Permite búsquedas avanzadas

## 5. Wazuh Dashboard
- Dashboards de:
  - Accesos fallidos
  - Accesos exitosos
  - Privilege escalation
  - Cambios de permisos
  - Accesos remotos
