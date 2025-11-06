# N8n-primer-flujo-astps
#  Flujo n8n - Registro de Gastos con Telegram y Google Sheets

Este flujo de **n8n** te permite registrar gastos fácilmente enviando mensajes a un **bot de Telegram**.  
Cada gasto se guarda automáticamente en una **hoja de Google Sheets**, y el bot responde confirmando el registro.  
Ideal para aprender cómo funciona n8n y automatizar tareas cotidianas.

---

##  Descripción general del flujo

**Estructura del flujo:**
Telegram Trigger → Function → Google Sheets
↘︎
→ Send Message

###  Funcionamiento
1. El usuario envía un mensaje al bot de Telegram con el formato:
   Gasto: <cantidad> <descripción>

2. El nodo **Function (Code)** interpreta el mensaje y genera un objeto con los campos:
- `fecha`
- `tipo`
- `cantidad`
- `descripcion`

3. El nodo **Google Sheets** añade una nueva fila en la hoja configurada, con las columnas:
   
4. Finalmente, el nodo **Send Message** envía una respuesta automática en Telegram:

   
---

## ⚙️ Requisitos

### 🔹 1. Bot de Telegram
- Crea tu bot desde [@BotFather](https://t.me/BotFather)
- Guarda el **Bot Token**
- Configura las credenciales en n8n (Telegram Bot API)

### 🔹 2. Google Sheets
- Crea una hoja con las columnas:
  fecha | tipo | cantidad | descripcion

- Comparte la hoja con el correo del **Service Account** de n8n (con permisos de editor)
- Añade la conexión de Google Sheets en n8n y selecciona tu documento

---

## 🚀 Cómo usar el flujo

1. **Importa** el archivo `.json` en tu n8n  
 → Ve a `Import → Import from file` y selecciona el flujo

2. **Conecta tus credenciales**:
 - Telegram Bot API
 - Google Sheets

3. **Activa el flujo** (toggle en la esquina superior derecha)

4. Envía un mensaje a tu bot con el formato:
   ✅ Automáticamente se añadirá una nueva fila en tu Google Sheets  
   ✅ Y el bot te responderá:  
   ✅ Gasto guardado correctamente




