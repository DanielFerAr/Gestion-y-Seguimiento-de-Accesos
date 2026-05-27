# 🔥 Incidente: Fuerza Bruta SSH en Linux

## 📝 Descripción
Se detectaron múltiples intentos fallidos de autenticación SSH en un servidor Linux, indicando un ataque de fuerza bruta.

---

## 🧪 Evidencia del incidente

### Logs relevantes
`Failed password for invalid user`

### Ejemplo de log
Failed password for root from 192.168.1.50 port 51234 ssh2

### Frecuencia
- 5 intentos fallidos en 2 minutos

---

## 🛡 Regla Wazuh activada
`300401 – Linux: Posible ataque de fuerza bruta SSH`

---

## 🧭 Análisis SOC
- El atacante intentó autenticarse como root.
- El origen proviene de una IP externa.
- No se observó autenticación exitosa posterior.

---

## ✔ Acciones recomendadas
- Bloquear IP origen.
- Deshabilitar login SSH para root.
- Habilitar fail2ban (opcional).
- Revisar logs de sudo y auth.log.

