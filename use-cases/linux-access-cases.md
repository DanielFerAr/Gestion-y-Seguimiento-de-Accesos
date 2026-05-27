# 🐧 Linux – Casos de Uso de Gestión y Seguimiento de Accesos

Este documento cubre los casos de uso relacionados con autenticación, sudo, cambios de usuarios y actividad sospechosa en Linux. Todos los casos están alineados con las reglas personalizadas de Wazuh y las reglas de auditd.

---

## 1. SSH fallido

### 🎯 Descripción
Detectar intentos fallidos de autenticación SSH.

### 🧪 Cómo reproducir
```bash
ssh usuario@IP
# ingresar contraseña incorrecta varias veces
