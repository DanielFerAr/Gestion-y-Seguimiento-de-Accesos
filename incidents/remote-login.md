# 🌐 Incidente: Inicio de Sesión Remoto Exitoso (RDP)

## 📝 Descripción
Se detectó un inicio de sesión remoto exitoso en un endpoint Windows mediante RDP.

---

## 🧪 Evidencia del incidente

### Log relevante
- EventID: **4624**
- LogonType: **10** (Remote Interactive)

### Ejemplo de log
An account was successfully logged on.

EventID: 4624

Logon Type: 10

Account Name: administrator

Source Network Address: 192.168.1.50

---

## 🛡 Regla Wazuh activada
`300310 – Windows: Inicio de sesión remoto exitoso`

---

## 🧭 Análisis SOC
- El usuario “administrator” inició sesión remotamente.
- La IP origen no pertenece a la red interna.
- No hubo intentos fallidos previos.

---

## ✔ Acciones recomendadas
- Validar si el acceso fue autorizado.
- Revisar actividad posterior del usuario.
- Revisar cambios en políticas de RDP.
