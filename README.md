# 📚 Sistema de Calificaciones - Dual Panel

Sistema integral de calificaciones con **acceso separado** para estudiantes y administradores (maestros).

## 🎯 Características Principales

### 👨‍🎓 Panel de ESTUDIANTES (Predeterminado)
- ✅ Consultar su propia calificación
- ✅ Ver estadísticas generales del grupo
- ✅ Interfaz simple e intuitiva
- ✅ Sin necesidad de contraseña

### 👨‍🏫 Panel de ADMINISTRADOR (Maestro)
- ✅ Acceso protegido con contraseña
- ✅ Consultar calificación de cualquier estudiante
- ✅ Ver lista completa de todos los estudiantes
- ✅ Agregar nuevos estudiantes
- ✅ Modificar calificaciones existentes
- ✅ Eliminar estudiantes
- ✅ Ver estadísticas detalladas del grupo

## 🔐 Credenciales de Acceso

### Administrador (Maestro)
- **Contraseña por defecto:** `admin123`
- Para cambiar la contraseña, edita la línea 8 del archivo `main.py`:
  ```python
  ADMIN_PASSWORD = "admin123"  # Cambia esto por tu contraseña
  ```

### Estudiantes
- No requieren contraseña
- Solo necesitan ingresar su nombre exactamente como aparece en el sistema (en MAYÚSCULAS)

## 🚀 Cómo Usar el Sistema

### Ejecutar el programa:
```bash
python3 main.py
```

### Menú Principal:
1. **Opción 1** - Acceso para Estudiantes (sin contraseña)
2. **Opción 2** - Acceso para Administrador (requiere contraseña)
3. **Opción 3** - Salir del sistema

## 📋 Funcionalidades Detalladas

### Para Estudiantes:
1. **Consultar mi calificación**: Ingresa tu nombre en MAYÚSCULAS y obtén tu calificación y estado (APROBADO/REPROBADO)
2. **Ver estadísticas del grupo**: Consulta el promedio del grupo, porcentaje de aprobados, mejor calificación, etc.

### Para Administradores:
1. **Consultar estudiante**: Buscar cualquier estudiante específico
2. **Ver todos los estudiantes**: Lista completa ordenada alfabéticamente
3. **Agregar estudiante**: Registrar nuevos estudiantes con sus calificaciones
4. **Modificar calificación**: Actualizar la calificación de un estudiante existente
5. **Eliminar estudiante**: Remover un estudiante del sistema (requiere confirmación)
6. **Estadísticas del grupo**: Ver análisis completo del desempeño del grupo

## 📊 Estructura de Datos

El sistema utiliza el archivo Excel `grupo001.xlsx` con la siguiente estructura:

| NOMBRE DE ALUMNO | CALIFICACION | PASÓ? |
|------------------|--------------|-------|
| JUAN PEREZ       | 7            | Aprobado |
| PEDRO MARTINEZ   | 4            | Reprobado |

## ⚙️ Requisitos

- Python 3.x
- Librería openpyxl

### Instalar dependencias:
```bash
pip install openpyxl
```

## 🎨 Características Especiales

- ✅ Interfaz con emojis para mejor experiencia visual
- ✅ Validación de datos de entrada
- ✅ Mensajes claros y descriptivos
- ✅ Confirmación para operaciones críticas (eliminar estudiantes)
- ✅ Limpieza automática de pantalla
- ✅ Sincronización automática con archivo Excel
- ✅ Seguridad con sistema de contraseñas para administradores
- ✅ Límite de intentos de inicio de sesión (3 intentos)

## 📝 Notas Importantes

1. **Los nombres deben ingresarse en MAYÚSCULAS** para que el sistema los reconozca correctamente
2. Las calificaciones deben estar entre **0 y 10**
3. La calificación mínima aprobatoria es **6.0**
4. Todos los cambios se guardan automáticamente en el archivo Excel
5. El sistema valida todos los datos ingresados

## 🔒 Seguridad

- El panel de administrador está protegido con contraseña
- Se permite un máximo de 3 intentos de inicio de sesión
- Las operaciones de eliminación requieren confirmación explícita
- Los estudiantes solo pueden ver su propia información

## 🆘 Solución de Problemas

### Si un estudiante no encuentra su nombre:
- Verificar que el nombre esté escrito exactamente como aparece en el Excel
- Asegurarse de escribir en MAYÚSCULAS
- Si el problema persiste, contactar al administrador

### Si olvidaste la contraseña de administrador:
- Edita el archivo `main.py`
- Busca la línea 8: `ADMIN_PASSWORD = "admin123"`
- Cámbiala por una nueva contraseña

## 📧 Soporte

Para cualquier duda o problema, contacta al desarrollador del sistema.

---

**Desarrollado con ❤️ para facilitar la gestión de calificaciones**
