# 🤖 Configuración de IA - PictoCom

## ¿Qué cambió?

Tu aplicación ahora usa **Google Gemini API (IA Gratuita)** para analizar el contexto de las frases en lugar de solo hacer comparaciones con artículos.

**Ventajas:**
✅ **Análisis contextual** - Entiende el significado completo de la frase, no solo palabras aisladas  
✅ **Pictogramas más coherentes** - Encuentra pictogramas realmente relevantes  
✅ **100% Gratuito** - Modelo Gemini 1.5 Flash con límite generoso (50 solicitudes/minuto)  
✅ **Fallback automático** - Si no hay conexión a internet, usa búsqueda simple  

---

## 📋 Pasos para activar (1-2 minutos)

### 1️⃣ Obtener API Key Gratuita

1. Ve a: **https://aistudio.google.com/app/apikey**
2. Haz clic en "Create API Key"
3. Selecciona "Create new API key in existing project" o crea un nuevo proyecto
4. **Copia la API Key** que se genera automáticamente

### 2️⃣ Configurar en tu aplicación

1. Abre `index.html` en un editor de texto
2. Encuentra esta línea (~línea 1253):
   ```javascript
   const GEMINI_API_KEY = 'AQUI_TU_API_KEY'; // REEMPLAZA CON TU API KEY
   ```
3. Reemplaza `AQUI_TU_API_KEY` con tu API key:
   ```javascript
   const GEMINI_API_KEY = 'AIza_1234567890abcdefghijklmnop-test'; // Tu API key aquí
   ```
4. **Guarda el archivo** (Ctrl+S)

### 3️⃣ ¡Listo! 🎉

- Recarga la página (`F5` o Ctrl+R)
- Prueba escribiendo una frase
- Verás que los pictogramas ahora son mucho más relevantes

---

## 🔍 ¿Cómo funciona?

### Sin IA (Fallback):
```
"Quiero ir al parque mañana" 
→ Extrae: "quiero", "ir", "parque"
```

### Con IA:
```
"Quiero ir al parque mañana"
→ IA analiza: "El usuario quiere ir a un lugar donde jugar/divertirse"
→ Extrae: "querer", "ir", "parque", "jugar"
→ Pictogramas más coherentes ✨
```

---

## ⚙️ Opciones avanzadas

### Ver si está usando IA:
- Abre la consola del navegador (`F12` → pestaña "Console")
- Si ves el mensaje "Gemini error, using fallback" → está usando fallback
- Si no ves errores → está funcionando correctamente

### Cambiar modelo de IA:
En la línea ~1257, puedes cambiar:
```javascript
GEMINI_API: 'https://generativelanguage.googleapis.com/v1beta/models/gemini-1.5-flash:generateContent',
```

Opciones disponibles (gratuitas):
- `gemini-1.5-flash` ← **Recomendado** (más rápido)
- `gemini-2.0-flash` (modelo más nuevo, más potente)
- `gemini-pro` (modelo anterior)

---

## 🛡️ Seguridad

- Tu API Key se usa **solo en tu navegador**
- Las solicitudes van **directamente a Google** desde tu dispositivo
- **No** guardamos historial de frases
- Datos: completamente privados en tu máquina

---

## ❓ Preguntas frecuentes

**P: ¿Se verá diferencia en los pictogramas?**  
R: ✅ Sí, especialmente en frases complejas o contextos especiales.

**P: ¿Qué pasa si agoto el límite gratuito?**  
R: El sistema detecta automáticamente y vuelve a usar búsqueda simple (sin IA).

**P: ¿Puedo compartir mi API Key?**  
R: ❌ **No**. Mantena segura. Si se expone, desactívala en Google AI Studio.

**P: ¿Funciona sin internet?**  
R: Parcialmente. Usa fallback simple con búsqueda básica.

---

## 📞 Soporte

Si algo no funciona:
1. Recarga la página completamente (`Ctrl+Shift+R`)
2. Comprueba que la API Key esté bien copiada (sin espacios)
3. Abre la consola (`F12`) y mira los mensajes de error

¡Listo para usar IA inteligente! 🚀
