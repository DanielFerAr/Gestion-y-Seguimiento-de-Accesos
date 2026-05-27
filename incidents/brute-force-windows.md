# 🔥 Incidente: Fuerza Bruta en Windows (RDP)

## 📝 Descripción
Se detectaron múltiples intentos fallidos de autenticación en un endpoint Windows, indicando un posible ataque de fuerza bruta vía RDP.

---

## 🧪 Evidencia del incidente

### Logs relevantes
- EventID: **4625** (Failed Logon)
- LogonType: **10** (RDP)
- 5 eventos en menos de 2 minutos

### Ejemplo de log
An account failed to log on.

EventID: 4625


Logon Type: 10

Account Name: administrator

Status: 0xC000006A


---

## 🛡 Regla Wazuh activada
`300301 – Windows: Posible ataque de fuerza bruta`

**Condición:**  
- 5 fallos (4625)  
- En 120 segundos  

---

## 🧭 Análisis SOC
- El atacante intentó autenticarse repetidamente vía RDP.
- El usuario objetivo era “administrator”.
- El origen del ataque proviene de una IP externa.
- No se observó login exitoso posterior.

---

## ✔ Acciones recomendadas
- Bloquear IP origen.
- Revisar firewall.
- Verificar si existen cuentas con contraseñas débiles.
- Revisar actividad posterior del usuario objetivo.
