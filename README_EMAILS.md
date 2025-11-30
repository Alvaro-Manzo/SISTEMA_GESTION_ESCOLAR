# 📧 Sistema de Notificaciones por Email - Guía Completa

Sistema para enviar calificaciones y números de cuenta a los estudiantes por correo electrónico.

## 🎯 Características

- ✅ **Envío masivo** de calificaciones a todos los estudiantes
- ✅ **Emails individuales** para casos específicos
- ✅ **Plantillas HTML profesionales** con diseño responsivo
- ✅ **Seguridad** usando contraseñas de aplicación de Gmail
- ✅ **Gestión de emails** de estudiantes
- ✅ **Estadísticas de envío** detalladas

## 📦 Instalación

### 1. Verificar que tienes los archivos:

```
CALIFICATIONS/
├── email_system.py        # Sistema de envío de emails
├── agregar_emails.py      # Gestor de emails de estudiantes
└── grupo001.xlsx          # Base de datos con estudiantes
```

### 2. No se requieren librerías adicionales

El sistema usa solo librerías estándar de Python:
- `smtplib` - Para enviar emails
- `email` - Para crear mensajes
- `openpyxl` - Ya instalado

## ⚙️ Configuración de Gmail

### Paso 1: Habilitar Verificación en 2 Pasos

1. Ve a tu cuenta de Google: https://myaccount.google.com
2. En el menú izquierdo, selecciona **"Seguridad"**
3. En "Cómo inicias sesión en Google", selecciona **"Verificación en dos pasos"**
4. Sigue las instrucciones para activarla

### Paso 2: Crear Contraseña de Aplicación

1. Una vez activada la verificación en 2 pasos, ve a:
   https://myaccount.google.com/apppasswords

2. En "Seleccionar app", elige **"Correo"**

3. En "Seleccionar dispositivo", elige **"Otro (nombre personalizado)"**
   - Escribe: "Sistema de Calificaciones"

4. Haz clic en **"Generar"**

5. **Copia la contraseña de 16 caracteres** que aparece
   - Ejemplo: `abcd efgh ijkl mnop`
   - ⚠️ Esta contraseña solo se muestra UNA VEZ

### Paso 3: Configurar el Sistema

1. Abre el archivo `email_system.py`

2. Busca esta sección (línea 20 aproximadamente):

```python
EMAIL_CONFIG = {
    'smtp_server': 'smtp.gmail.com',
    'puerto': 587,
    'remitente_email': 'tu_email@gmail.com',  # TU EMAIL AQUÍ
    'remitente_password': 'tu_contraseña_de_aplicacion',  # CONTRASEÑA AQUÍ
    'remitente_nombre': 'Sistema de Calificaciones'
}
```

3. Reemplaza:
   - `tu_email@gmail.com` → Tu email de Gmail
   - `tu_contraseña_de_aplicacion` → La contraseña de 16 caracteres
   - (Opcional) Cambia el nombre del remitente

**Ejemplo configurado:**
```python
EMAIL_CONFIG = {
    'smtp_server': 'smtp.gmail.com',
    'puerto': 587,
    'remitente_email': 'profesor@gmail.com',
    'remitente_password': 'abcd efgh ijkl mnop',
    'remitente_nombre': 'Profesor Juan Pérez'
}
```

## 📝 Agregar Emails de Estudiantes

### Opción 1: Usando el script (Recomendado)

```bash
python3 agregar_emails.py
```

El script te permite:
- **Opción 1**: Agregar emails manualmente uno por uno
- **Opción 2**: Generar emails automáticamente con un dominio
  - Ejemplo: Si el dominio es `estudiantes.edu.mx`
  - JUAN PEREZ → `juan.perez@estudiantes.edu.mx`

### Opción 2: Manualmente en Excel

1. Abre `grupo001.xlsx`
2. La columna **E** debe tener el encabezado **"EMAIL"**
3. Agrega los emails de cada estudiante en su fila correspondiente
4. Guarda el archivo

**Ejemplo:**

| NOMBRE | CALIFICACION | PASÓ? | NUMERO DE CUENTA | EMAIL |
|--------|--------------|-------|------------------|-------|
| JUAN PEREZ | 7 | Aprobado | 324056192 | juan.perez@email.com |
| PEDRO MARTINEZ | 4 | Reprobado | 324077528 | pedro.martinez@email.com |

## 🚀 Uso del Sistema

### 1. Ejecutar el Sistema de Emails

```bash
python3 email_system.py
```

### 2. Menú Principal

```
📧 SISTEMA DE NOTIFICACIONES POR EMAIL

1. 📤 Enviar calificaciones a todos los estudiantes
2. 📧 Enviar email a un estudiante específico
3. ⚙️  Agregar columna EMAIL al Excel
4. 🔧 Verificar configuración
5. 🚪 Salir
```

### 3. Opciones Detalladas

#### Opción 1: Envío Masivo
- Envía un email a **TODOS** los estudiantes que tengan email registrado
- Incluye:
  - Nombre del estudiante
  - Calificación
  - Estado (APROBADO/REPROBADO)
  - Número de cuenta
  - Instrucciones de acceso al sistema
- Muestra estadísticas al finalizar

#### Opción 2: Envío Individual
- Para enviar a un estudiante específico
- Útil para:
  - Reenvíos
  - Nuevos estudiantes
  - Correcciones

#### Opción 3: Agregar Columna EMAIL
- Crea la columna EMAIL en el Excel si no existe

#### Opción 4: Verificar Configuración
- Verifica que el email y contraseña estén configurados
- Muestra la configuración actual

## 📧 Ejemplo de Email Enviado

Los estudiantes recibirán un email profesional en HTML con:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
        📚 Sistema de Calificaciones
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Hola JUAN PEREZ,

📋 Tu Información:
   👤 Estudiante: JUAN PEREZ
   📝 Calificación: 7.0
   📊 Estado: 🎉 APROBADO

🔐 Tu Número de Cuenta (CONFIDENCIAL)
   ┌─────────────────┐
   │   324056192     │
   └─────────────────┘

⚠️ Este número es personal e intransferible

📱 Cómo acceder al sistema:
   1. Ejecuta el sistema de calificaciones
   2. Selecciona "Acceso para ESTUDIANTES"
   3. Ingresa tu número: 324056192
   4. Consulta tu información

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

## 📊 Estadísticas de Envío

Al finalizar el envío masivo, verás:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📊 RESUMEN DEL ENVÍO
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Total de estudiantes: 27
✅ Enviados exitosamente: 25
❌ Fallidos: 0
⊘  Sin email: 2
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

## 🔒 Seguridad y Mejores Prácticas

### ✅ Hacer:
- Usar contraseña de aplicación (NO tu contraseña de Gmail)
- Mantener el archivo `email_system.py` seguro
- Verificar los emails antes de enviar masivamente
- Hacer backup del Excel antes de modificarlo

### ❌ NO Hacer:
- Compartir tu contraseña de aplicación
- Usar tu contraseña principal de Gmail
- Enviar emails sin verificar la configuración
- Subir el archivo con credenciales a repositorios públicos

## 🔧 Solución de Problemas

### Error: "Authentication failed"
- **Causa**: Contraseña incorrecta o no configurada
- **Solución**: 
  1. Verifica que copiaste bien la contraseña de aplicación
  2. Asegúrate de no tener espacios extra
  3. Regenera la contraseña de aplicación si es necesario

### Error: "SMTP connection failed"
- **Causa**: Problema de conexión a internet
- **Solución**: Verifica tu conexión y cortafuegos

### Los emails no llegan
- **Revisa**:
  1. Carpeta de SPAM/Correo no deseado
  2. Que los emails estén bien escritos
  3. Que Gmail no esté bloqueando envíos masivos

### Error: "Column EMAIL not found"
- **Causa**: Falta la columna EMAIL en el Excel
- **Solución**: Ejecuta la opción 3 del menú principal

## 📈 Consejos Pro

### 1. Envío Escalonado
Si tienes muchos estudiantes (>50), considera:
- Enviar en grupos pequeños
- Aumentar el tiempo de espera entre emails (línea 280 en `email_system.py`)

### 2. Personalización
Puedes modificar:
- **Diseño del email**: Edita la función `generar_email_calificacion()`
- **Asunto**: Línea 279
- **Colores**: Sección CSS del HTML

### 3. Logs
El sistema imprime en consola cada email enviado:
```
✅ JUAN PEREZ                     → juan.perez@email.com
✅ PEDRO MARTINEZ                 → pedro.martinez@email.com
```

### 4. Testing
Antes del envío masivo:
1. Usa la opción 2 (envío individual)
2. Envíate un email de prueba a ti mismo
3. Verifica que todo se vea bien

## 🔗 Integración con el Sistema Principal

Puedes integrar el envío de emails en `main.py`:

```python
from email_system import GestorEmails

# En el panel de admin, agregar opción:
def enviar_calificacion_por_email(estudiante):
    gestor = GestorEmails()
    info = estudiantes[estudiante]
    email = info.get('email')
    
    if email:
        gestor.enviar_email_individual(
            email,
            estudiante,
            info['calificacion'],
            info['estado'],
            info['numero_cuenta']
        )
```

## 📞 Límites de Gmail

Gmail tiene límites de envío:
- **Cuentas gratuitas**: ~500 emails/día
- **Google Workspace**: ~2000 emails/día

Si tienes muchos estudiantes, considera:
- Dividir el envío en varios días
- Usar un servicio profesional de email (SendGrid, Mailgun, etc.)

## 🎓 Flujo Completo Recomendado

1. **Preparación**:
   ```bash
   python3 generar_cuentas.py  # Genera números de cuenta
   python3 agregar_emails.py   # Agrega emails
   ```

2. **Configuración**:
   - Configurar Gmail según esta guía
   - Editar `email_system.py` con tus credenciales

3. **Prueba**:
   ```bash
   python3 email_system.py
   # Opción 4: Verificar configuración
   # Opción 2: Enviar email de prueba a ti mismo
   ```

4. **Envío Masivo**:
   ```bash
   python3 email_system.py
   # Opción 1: Enviar a todos
   ```

## 📄 Archivos del Sistema

```
email_system.py       - Sistema principal de envío
agregar_emails.py     - Gestor de emails de estudiantes
README_EMAILS.md      - Esta guía
grupo001.xlsx         - Base de datos (debe tener columna EMAIL)
credenciales_estudiantes.txt - Números de cuenta generados
```

## 🎉 ¡Listo!

Ahora tienes un sistema completo para notificar a tus estudiantes por email con:
- ✅ Sus calificaciones
- ✅ Sus números de cuenta
- ✅ Instrucciones de acceso
- ✅ Diseño profesional

---

**Última actualización:** 30 de noviembre de 2025  
**Versión:** 1.0  
**Compatibilidad:** Python 3.6+
