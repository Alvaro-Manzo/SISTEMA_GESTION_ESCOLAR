# 🚀 Sistema de Calificaciones PRO 2.0 - Versión Profesional

Sistema integral de gestión de calificaciones académicas con arquitectura empresarial, logging avanzado, backups automáticos y exportación de reportes.

## ✨ Características PRO

### 🏗️ Arquitectura Profesional
- ✅ **Programación Orientada a Objetos** - Código modular y reutilizable
- ✅ **Gestor de Configuración** - Archivo JSON para configuraciones
- ✅ **Sistema de Logging** - Registro completo de operaciones
- ✅ **Backups Automáticos** - Respaldo antes de cada modificación
- ✅ **Manejo de Errores Robusto** - Try-catch en todas las operaciones críticas
- ✅ **Type Hints** - Código más legible y mantenible

### 🎨 Interfaz Mejorada
- ✅ **Colores en Terminal** - Usando colorama (con fallback si no está instalado)
- ✅ **Mensajes Contextuales** - Éxito, error, advertencia, info
- ✅ **UI Consistente** - Headers, subheaders y formato uniforme
- ✅ **Animaciones Suaves** - Transiciones entre menús

### 🔐 Seguridad Avanzada
- ✅ **Contraseña Configurable** - Desde archivo JSON
- ✅ **Límite de Intentos** - Protección contra fuerza bruta
- ✅ **Input Oculto** - Contraseña no visible (getpass)
- ✅ **Logging de Accesos** - Auditoría completa

### 💾 Gestión de Datos
- ✅ **Backups Automáticos** - Antes de cada modificación
- ✅ **Gestión de Backups** - Límite configurable, limpieza automática
- ✅ **Exportación a CSV** - Reportes en formato universal
- ✅ **Reportes de Texto** - Estadísticas completas en TXT
- ✅ **Sincronización Excel** - Guardado inteligente con validación

### 📊 Reportes y Estadísticas
- ✅ **Estadísticas Detalladas** - Promedios, máximos, mínimos, porcentajes
- ✅ **Exportación CSV** - Compatible con Excel/Sheets
- ✅ **Reportes de Texto** - Documentación completa
- ✅ **Timestamps** - Fecha y hora en todos los reportes

### 📝 Sistema de Logs
- ✅ **Logs Automáticos** - Todas las operaciones registradas
- ✅ **Niveles de Log** - INFO, WARNING, ERROR, CRITICAL
- ✅ **Logs por Día** - Archivo separado cada día
- ✅ **Visualización in-app** - Ver logs desde el panel admin

## 📦 Instalación

### 1. Clonar o descargar el proyecto

```bash
cd /Users/omanzo/VISUALSTUDIOCODE/CALIFICATIONS
```

### 2. Instalar dependencias

```bash
pip install -r requirements.txt
```

O instalar manualmente:

```bash
pip install openpyxl colorama
```

**Nota:** Si no instalas `colorama`, el sistema funcionará sin colores (fallback automático).

### 3. Verificar archivos

Asegúrate de tener:
- ✅ `main_pro.py` - Sistema principal
- ✅ `config.json` - Configuración
- ✅ `grupo001.xlsx` - Base de datos de estudiantes
- ✅ `requirements.txt` - Dependencias

## 🚀 Ejecución

### Versión PRO (Recomendada)
```bash
python3 main_pro.py
```

### Versión Básica
```bash
python3 main.py
```

## 📋 Estructura del Proyecto

```
CALIFICATIONS/
├── main_pro.py              # Sistema PRO (nuevo)
├── main.py                  # Sistema básico (anterior)
├── config.json              # Configuración del sistema
├── grupo001.xlsx            # Base de datos Excel
├── requirements.txt         # Dependencias Python
├── README.md                # Documentación completa
├── README_PRO.md           # Este archivo
│
├── backups/                # Backups automáticos
│   ├── backup_20250429_143022.xlsx
│   └── ...
│
├── logs/                   # Logs del sistema
│   ├── sistema_20250429.log
│   └── ...
│
└── reportes/               # Reportes exportados
    ├── reporte_20250429_143022.csv
    ├── estadisticas_20250429_143022.txt
    └── ...
```

## ⚙️ Configuración (config.json)

### Seguridad
```json
"seguridad": {
  "admin_password": "admin123",      // Cambiar contraseña aquí
  "max_intentos_login": 3,
  "timeout_sesion": 300
}
```

### Calificaciones
```json
"calificaciones": {
  "minima_aprobatoria": 6.0,         // Calificación mínima para aprobar
  "maxima": 10.0,
  "minima": 0.0,
  "decimales": 2
}
```

### Backups
```json
"backups": {
  "automaticos": true,               // Activar/desactivar backups
  "max_backups": 10,                 // Número máximo de backups
  "formato_nombre": "backup_%Y%m%d_%H%M%S.xlsx"
}
```

### Interfaz
```json
"interfaz": {
  "usar_colores": true,              // Activar/desactivar colores
  "animaciones": true,
  "limpiar_pantalla": true
}
```

## 🎯 Funcionalidades por Panel

### 👨‍🎓 Panel de ESTUDIANTES

1. **Consultar mi calificación**
   - Sin contraseña
   - Solo ingresar nombre
   - Ver calificación y estado

2. **Ver estadísticas del grupo**
   - Promedio general
   - Porcentaje de aprobados
   - Mejor calificación

3. **Volver al menú principal**

### 👨‍🏫 Panel de ADMINISTRADOR (Contraseña: admin123)

1. **Consultar estudiante**
   - Buscar cualquier estudiante
   - Ver información completa

2. **Ver todos los estudiantes**
   - Lista ordenada alfabéticamente
   - Calificaciones y estados
   - Con colores (verde=aprobado, rojo=reprobado)

3. **Agregar estudiante**
   - Validación de datos
   - Actualización automática del Excel
   - Backup automático

4. **Modificar calificación**
   - Muestra calificación actual
   - Validación de rango (0-10)
   - Log de cambios

5. **Eliminar estudiante**
   - Requiere confirmación
   - Backup automático
   - Log de eliminación

6. **Estadísticas del grupo**
   - Análisis completo
   - Promedios y porcentajes
   - Mejores estudiantes

7. **Gestión de backups** ⭐ NUEVO
   - Ver lista de backups
   - Información de tamaño y fecha
   - Ubicación de archivos

8. **Ver logs del sistema** ⭐ NUEVO
   - Últimas 20 entradas
   - Consulta rápida desde la app
   - Ubicación del archivo completo

9. **Volver al menú principal**

### 📊 Panel de REPORTES ⭐ NUEVO

1. **Exportar a CSV**
   - Formato compatible con Excel
   - Todos los estudiantes
   - Timestamp en nombre

2. **Exportar estadísticas completas**
   - Archivo de texto detallado
   - Estadísticas generales
   - Lista completa de estudiantes

## 📝 Sistema de Logs

### Ubicación
```
logs/sistema_YYYYMMDD.log
```

### Qué se registra:
- ✅ Inicio y cierre del sistema
- ✅ Accesos de administrador (exitosos y fallidos)
- ✅ Consultas de estudiantes
- ✅ Operaciones CRUD (Crear, Leer, Actualizar, Eliminar)
- ✅ Creación de backups
- ✅ Exportación de reportes
- ✅ Errores y excepciones

### Ejemplo de log:
```
[2025-11-29 14:30:22] INFO: Sistema iniciado
[2025-11-29 14:30:45] INFO: Datos cargados: 27 estudiantes
[2025-11-29 14:31:10] INFO: Acceso de administrador concedido
[2025-11-29 14:31:45] INFO: Estudiante agregado: MARIA LOPEZ - Calificación: 8.5
[2025-11-29 14:32:15] INFO: Backup creado: backup_20250429_143215.xlsx
```

## 💾 Sistema de Backups

### Automáticos
- Se crea un backup antes de:
  - Agregar estudiante
  - Modificar calificación
  - Eliminar estudiante

### Gestión
- Máximo 10 backups (configurable)
- Limpieza automática de antiguos
- Nombrado con timestamp
- Ubicación: `backups/`

### Restaurar un backup
```bash
cp backups/backup_20250429_143215.xlsx grupo001.xlsx
```

## 🎨 Personalización

### Cambiar Colores
Editar en `main_pro.py`:
```python
Fore.GREEN   # Verde
Fore.RED     # Rojo
Fore.YELLOW  # Amarillo
Fore.CYAN    # Cian
Fore.MAGENTA # Magenta
Fore.BLUE    # Azul
```

### Agregar Nuevas Funciones
1. Crear método en clase `SistemaCalificaciones`
2. Agregar opción en el menú correspondiente
3. Actualizar documentación

## 🔧 Solución de Problemas

### Colores no funcionan
```bash
pip install colorama
```

### Archivo no encontrado
- Verificar que `grupo001.xlsx` existe
- Revisar path en `config.json`

### Error de permisos
```bash
chmod 755 main_pro.py
```

### Ver logs completos
```bash
cat logs/sistema_20250429.log
```

## 📈 Comparación de Versiones

| Característica | Básica | PRO |
|----------------|--------|-----|
| Panel dual (estudiante/admin) | ✅ | ✅ |
| Gestión de calificaciones | ✅ | ✅ |
| Estadísticas | ✅ | ✅ |
| Backups automáticos | ❌ | ✅ |
| Sistema de logs | ❌ | ✅ |
| Exportar reportes | ❌ | ✅ |
| Configuración JSON | ❌ | ✅ |
| Colores en terminal | ❌ | ✅ |
| Arquitectura OOP | ❌ | ✅ |
| Type hints | ❌ | ✅ |
| Gestión de backups | ❌ | ✅ |
| Ver logs in-app | ❌ | ✅ |

## 🚀 Mejoras Futuras Posibles

- [ ] Base de datos SQLite en lugar de Excel
- [ ] Interfaz web con Flask/Django
- [ ] Autenticación con JWT
- [ ] API REST
- [ ] Dashboard con gráficos
- [ ] Notificaciones por email
- [ ] Exportación a PDF
- [ ] Sistema de calificaciones parciales
- [ ] Historial de cambios por estudiante
- [ ] Múltiples grupos/materias

## 👨‍💻 Desarrollo

### Estructura de Clases

```python
ConfigManager      # Gestión de configuración
LogManager         # Sistema de logging
BackupManager      # Backups automáticos
InterfazUI         # Interfaz con colores
SistemaCalificaciones  # Lógica principal
```

### Flujo de Ejecución

```
main() 
  → SistemaCalificaciones.__init__()
    → ConfigManager.cargar_config()
    → LogManager.setup_logging()
    → BackupManager.__init__()
  → ejecutar()
    → cargar_datos_excel()
    → Mostrar menú
    → Procesar opciones
    → Guardar cambios (con backup)
```

## 📞 Soporte

Para reportar bugs o sugerir mejoras, contacta al desarrollador.

## 📄 Licencia

Sistema desarrollado para uso educativo.

---

**🎓 Sistema de Calificaciones PRO 2.0**  
*Desarrollado con ❤️ y tecnología de nivel empresarial*

**Última actualización:** 29 de noviembre de 2025
