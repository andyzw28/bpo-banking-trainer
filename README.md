# 🏦 BancaEntrenador — Simulador BPO Banking

Simulador de entrenamiento para agentes BPO del sector financiero. Permite practicar conversaciones con clientes simulados por IA en escenarios reales bancarios.

---

## 🚀 Acceso rápido

👉 **[Abrir simulador](https://TU-USUARIO.github.io/bpo-banking-trainer)**

---

## 🎯 ¿Para qué sirve?

Herramienta de entrenamiento para equipos BPO bancarios. Cada agente practica de forma autónoma conversaciones difíciles antes de atender clientes reales.

### Escenarios disponibles
| Categoría | Escenario | Dificultad |
|-----------|-----------|------------|
| 🔴 Fraude | Cliente reporta cargos no reconocidos | ●●● |
| 🔵 Crédito | Solicitud de préstamo personal urgente | ●●○ |
| 🟠 PQR | Cliente molesto por cobro incorrecto | ●●● |
| 🟢 Inversión | Asesoría para invertir ahorros en CDT | ●●○ |
| 🟡 Operaciones | Transferencia internacional urgente | ●●● |

### Funcionalidades
- 💬 Chat en tiempo real con cliente simulado por IA (Claude)
- 📋 Base de conocimiento bancaria integrada
- ✅ Checklist de protocolo por escenario
- 📊 Evaluación automática por sesión
- 🔁 Repetición ilimitada de escenarios

---

## 📁 Estructura del repositorio

```
bpo-banking-trainer/
├── index.html        ← Toda la aplicación (un solo archivo)
└── README.md         ← Este archivo
```

---

## ⚙️ Configuración inicial

### 1. Clona o descarga el repositorio
```bash
git clone https://github.com/TU-USUARIO/bpo-banking-trainer.git
```

### 2. Agrega tu API Key de Anthropic
Abre `index.html` y busca la línea:
```javascript
headers: { 'Content-Type': 'application/json' },
```
Agrégale tu API key:
```javascript
headers: {
  'Content-Type': 'application/json',
  'x-api-key': 'sk-ant-TU-API-KEY-AQUI',
  'anthropic-version': '2023-06-01'
},
```
> ⚠️ **Nota:** Para producción se recomienda usar un backend proxy para no exponer la API key. Para uso interno de equipo es suficiente.

### 3. Activa GitHub Pages
1. Ve a **Settings** → **Pages**
2. Source: `Deploy from a branch`
3. Branch: `main` / `root`
4. Guarda — en ~2 minutos tendrás la URL pública

### 4. Comparte en Google Sites
1. Abre tu Google Site
2. **Insertar → Botón** o **Insertar → Incrustar**
3. Pega la URL de GitHub Pages
4. Publica el sitio

---

## 🧠 Personalización

### Agregar un nuevo escenario
En `index.html`, dentro del array `SCENARIOS`, agrega un objeto:

```javascript
{
  id: 'nuevo1',
  tag: 'account',          // fraud | loan | complaint | invest | account
  tagLabel: 'Operaciones',
  name: 'Nombre del escenario',
  difficulty: 2,           // 1, 2 o 3
  clientName: 'Nombre Cliente',
  clientInitial: 'NC',
  clientInfo: 'Descripción breve del cliente',
  opening: 'Primer mensaje del cliente...',
  systemPrompt: `Instrucciones para la IA que simula al cliente...`,
  suggestions: ['Respuesta sugerida 1', 'Respuesta sugerida 2'],
  checklist: ['Paso de protocolo 1', 'Paso de protocolo 2']
}
```

### Agregar artículo a la base de conocimiento
En el array `KB`:

```javascript
{
  id: 'nuevo_articulo',
  title: 'Título del artículo',
  tags: ['etiqueta1', 'etiqueta2'],
  body: `Contenido completo del procedimiento...`
}
```

---

## 🔒 Seguridad y acceso

- Para uso **solo interno**: configura el repositorio como **privado** y GitHub Pages estará disponible únicamente para colaboradores.
- Para uso **libre en el equipo**: repositorio público o privado con GitHub Pages habilitado basta.
- La API key de Anthropic genera costos por uso. Monitorea en [console.anthropic.com](https://console.anthropic.com).

---

## 📬 Soporte

Creado con Claude (Anthropic) · Adaptable a cualquier vertical BPO
