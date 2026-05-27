# 🏗️ Arquitectura del Laboratorio – Gestión y Seguimiento de Accesos

Este laboratorio SOC está diseñado para centralizar, monitorear y detectar eventos relacionados con accesos en sistemas Windows y Linux. La arquitectura se basa en un pipeline de recolección, normalización y análisis de logs orientado exclusivamente a autenticación, permisos y privilegios.

---

## 🔹 Componentes principales

### 1. Wazuh Manager
- Recibe logs de los agentes.
- Normaliza eventos.
- Aplica reglas personalizadas de accesos.
- Genera alertas.

### 2. Wazuh Indexer & Dashboard
- Almacena eventos.
- Permite visualización mediante dashboards.
- Facilita análisis de incidentes.

### 3. Windows Endpoint
- Sysmon (config optimizada para accesos).
- Windows Event Logs (4624, 4625, 4672, 4720, 4726, 4728).
- Wazuh Agent.

### 4. Linux Endpoint
- auditd (reglas optimizadas para accesos).
- auth.log.
- Wazuh Agent.

---

## 🔹 Diagrama general de arquitectura

El diagrama se encuentra en:

- `architecture-diagram.mmd`
- `architecture-diagram.png`

---

## 🔹 Flujo de datos

1. El usuario intenta autenticarse en Windows o Linux.
2. El sistema genera logs (Sysmon, Event Logs, auditd).
3. El agente Wazuh envía los eventos al Manager.
4. El Manager aplica reglas de detección.
5. Los eventos y alertas se almacenan en el Indexer.
6. El analista visualiza accesos y alertas en el Dashboard.

El flujo completo está en `data-flow.mmd`.

---

## 🔹 Objetivo de la arquitectura

- Detectar accesos válidos e inválidos.
- Identificar elevación de privilegios.
- Registrar cambios de usuarios y grupos.
- Monitorear accesos remotos.
- Proveer visibilidad completa del ciclo de vida de accesos.

Esta arquitectura simula el funcionamiento real de un SOC enfocado en Access Monitoring.
