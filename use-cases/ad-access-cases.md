# 🏢 Active Directory – Casos de Uso de Accesos

Este documento cubre los casos de uso relacionados con autenticación, cambios de permisos y gestión de cuentas dentro de un entorno Active Directory.

---

## 1. Creación de usuario en AD

### 🎯 Descripción
Detectar cuando se crea un usuario en el dominio.

### 🧪 Cómo reproducir
```powershell
New-ADUser -Name "TestUser" -AccountPassword (Read-Host -AsSecureString)
