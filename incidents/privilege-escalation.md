# ⚠️ Incidente: Elevación de Privilegios

## 📝 Descripción
Se detectó un intento de elevación de privilegios en un endpoint Linux mediante el uso de sudo.

---

## 🧪 Evidencia del incidente

### Log relevante
sudo:   testuser : TTY=pts/0 ; COMMAND=/usr/bin/ls /root

### Archivos monitoreados
- `/var/log/auth.log`
- auditd rules

---

## 🛡 Regla Wazuh activada
`300200 – Linux: Uso de sudo detectado`

---

## 🧭 Análisis SOC
- El usuario “testuser” intentó acceder al directorio `/root`.
- El comando ejecutado requiere privilegios elevados.
- No se observó actividad adicional sospechosa.

---

## ✔ Acciones recomendadas
- Validar si el usuario debía tener permisos sudo.
- Revisar historial de comandos.
- Revisar cambios recientes en `/etc/sudoers`.
