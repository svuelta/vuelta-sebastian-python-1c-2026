# Encuentro 2 — Python aplicado para automatización y desarrollo

**Python, Datos e Ingeniería de IA Aplicada — UTN Rosario · FRRO**  
Área de Extensión Universitaria · Matías Barreto, 2026

Dominio del lenguaje Python para resolver problemas reales: tipos, estructuras de control, funciones, manejo de archivos, JSON, excepciones y consumo de APIs. Cierre con un script integrador que consolida todo lo aprendido y se commitea al repositorio de la cursada.

---

## Contenido

| Notebook | Tema |
|---|---|
| `001_lenguaje` | Tipos de datos, estructuras de control (if / for) y funciones — dominio: registro de participantes |
| `002_memoria` | Archivos de texto, JSON y manejo de excepciones — dominio: campaña de salud comunitaria |
| `003_servicios` | Módulos de la biblioteca estándar y consumo de APIs — dominio: pronóstico agroclimático con Open-Meteo |
| `004_integrador` | Pipeline completo: carga de datos + API + reporte + commit al repositorio |

---

## API utilizada

**Open-Meteo** — pronóstico meteorológico de código abierto.

- Sin API key, sin registro requerido
- Documentación: [open-meteo.com/en/docs](https://open-meteo.com/en/docs)
- Los notebooks consultan coordenadas de la región de Rosario (configurable)

---

## Cómo descargar esta carpeta

Esta es una subcarpeta dentro de un repositorio más grande. Para descargarla sola sin clonar todo el repositorio, hay dos herramientas web gratuitas que no requieren registro:

### Opción 1 — Download Directory

1. Copiá el enlace completo de esta carpeta en GitHub.
2. Entrá en **[download-directory.github.io](https://download-directory.github.io)**.
3. Pegá la URL en el cuadro de búsqueda y presioná Enter.
4. Se descarga automáticamente un `.zip` con únicamente esta carpeta.

### Opción 2 — DownGit

1. Entrá en **[downgit.github.io](https://downgit.github.io)**.
2. Pegá el enlace de la carpeta en el campo *GitHub URL*.
3. Hacé clic en **Download**.

---

## Configuración del entorno local

### Requisitos previos

- **Python 3.12 o superior** — [python.org/downloads](https://www.python.org/downloads/)
- **uv** — gestor de entornos virtuales ultrarrápido
- Conexión a Internet (para `003_servicios` y `004_integrador`)

---

### Paso 1 — Instalar uv

**Linux / macOS:**
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

**Windows (PowerShell):**
```powershell
powershell -c "irm https://astral.sh/uv/install.ps1 | iex"
```

**Alternativa universal** (si ya tenés pip):
```bash
pip install uv
```

Verificá la instalación:
```bash
uv --version
```

---

### Paso 2 — Crear el entorno virtual

Desde la carpeta `002 - clase 2/`:

```bash
uv venv .venv
```

---

### Paso 3 — Activar el entorno

**Linux / macOS:**
```bash
source .venv/bin/activate
```

**Windows (CMD):**
```cmd
.venv\Scripts\activate.bat
```

**Windows (PowerShell):**
```powershell
.venv\Scripts\Activate.ps1
```

El prompt de la terminal va a mostrar `(.venv)` cuando el entorno esté activo.

---

### Paso 4 — Instalar las dependencias

Este proyecto usa `requirements.txt` directamente, **sin `pyproject.toml`**.  
El comando de instalación con uv es:

```bash
uv pip install -r requirements.txt
```

> ✦ Diferencia clave con otros proyectos:
> - Con `pyproject.toml` se usa `uv sync`
> - Con `requirements.txt` se usa `uv pip install -r requirements.txt`
>
> Ambos crean el mismo entorno aislado — solo cambia el origen de la lista de dependencias.

---

### Paso 5 — Abrir los notebooks

```bash
jupyter lab
```

O si preferís la interfaz clásica:
```bash
jupyter notebook
```

---

### Desactivar el entorno cuando terminás

```bash
deactivate
```
