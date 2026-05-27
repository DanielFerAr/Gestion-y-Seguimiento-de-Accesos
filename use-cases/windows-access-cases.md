# 🪟 Windows – Casos de Uso de Gestión y Seguimiento de Accesos

Este documento describe los casos de uso relacionados con accesos en sistemas Windows, alineados a los eventos críticos del Security Log y a las reglas personalizadas de Wazuh.

---

## 1. Creación de usuario (EventID 4720)

### 🎯 Descripción
Detectar cuando se crea una nueva cuenta de usuario en el sistema.

### 🧪 Cómo reproducir
```cmd
net user testuser /add
