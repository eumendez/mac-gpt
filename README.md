# 🎓 ETL Web MAC - Sistema Inteligente de Datos Académicos

<div align="center">

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://python.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Status](https://img.shields.io/badge/Status-Active-green.svg)]()

*Una solución ETL completa para extraer, transformar y cargar datos del plan de estudios de Matemáticas Aplicadas y Computación (MAC) de la FES Acatlán, potenciada con inteligencia artificial a través de MAC-GPT.*

</div>

---

## 📋 Tabla de Contenidos

- [🎯 Descripción del Proyecto](#-descripción-del-proyecto)
- [✨ Características Principales](#-características-principales)
- [🏗️ Arquitectura del Sistema](#️-arquitectura-del-sistema)
- [🛠️ Tecnologías Utilizadas](#️-tecnologías-utilizadas)
- [📋 Requisitos del Sistema](#-requisitos-del-sistema)
- [🚀 Instalación y Configuración](#-instalación-y-configuración)
- [💻 Guía de Uso](#-guía-de-uso)
- [📊 Ejemplos de Uso](#-ejemplos-de-uso)
- [🤝 Contribuir](#-contribuir)
- [📝 Licencia](#-licencia)
- [👥 Autores](#-autores)

## 🎯 Descripción del Proyecto

**ETL Web MAC** es un sistema integral de procesamiento de datos académicos diseñado específicamente para la carrera de Matemáticas Aplicadas y Computación de la FES Acatlán. Combina técnicas avanzadas de extracción de datos web y procesamiento de documentos PDF con inteligencia artificial para crear un asistente virtual inteligente.

### 🎯 Objetivos Principales

- **Automatizar** la extracción de información académica desde múltiples fuentes
- **Centralizar** los datos del plan de estudios en formatos estructurados
- **Facilitar** el acceso a información académica mediante un chatbot inteligente
- **Proporcionar** una interfaz web moderna para consultas interactivas

## ✨ Características Principales

### 🔄 Pipeline ETL Robusto
- **Extracción automática** de datos desde sitios web institucionales
- **Procesamiento inteligente** de documentos PDF académicos
- **Transformación** de datos con generación de embeddings para búsqueda semántica
- **Carga** en múltiples formatos (CSV, Pickle, JSON)

### 🤖 MAC-GPT - Asistente Inteligente
- **Chatbot conversacional** potenciado por Google Gemini
- **Búsqueda semántica** en documentos académicos
- **Interfaz web moderna** y responsive
- **CLI interactiva** para uso programático

### 📊 Gestión de Datos
- **Esquemas OLTP y OLAP** para análisis dimensional
- **Versionado de datos** con pickle y CSV
- **Validación automática** de integridad de datos

## 🏗️ Arquitectura del Sistema

```
proyecto-examen/
├── 📁 config/                  # Configuraciones globales del sistema
│   ├── __init__.py
│   └── settings.py            # Variables de configuración centralizadas
│
├── 📁 data/                   # Repositorio de datos del proyecto
│   ├── 📁 csv/               # Datos procesados en formato CSV
│   ├── 📁 olap/              # Esquemas OLAP para análisis dimensional
│   ├── 📁 oltp/              # Esquemas OLTP normalizados
│   ├── 📁 output/            # Resultados de extracción
│   ├── 📁 pdfs/              # Documentos PDF organizados por semestre
│   └── 📁 pickles/           # Datos serializados para carga rápida
│
├── 📁 src/                    # Código fuente principal
│   ├── 📁 chatbot/           # Sistema MAC-GPT
│   │   ├── cli.py            # Interfaz de línea de comandos
│   │   ├── mac_gpt.py        # Motor del chatbot
│   │   └── 📁 web/           # Interfaz web del chatbot
│   ├── 📁 extractors/        # Módulos de extracción de datos
│   ├── 📁 loaders/           # Gestores de carga de datos
│   └── 📁 transformers/      # Procesadores y transformadores
│
├── 📁 pipeline/               # Scripts del pipeline ETL
│   ├── extract.py            # Fase de extracción
│   └── transform.py          # Fase de transformación
│
├── 📄 main.py                 # Punto de entrada principal
├── 📄 requirements.txt       # Dependencias de Python
├── 📄 pyproject.toml         # Configuración del proyecto (Poetry)
└── 📄 env.example            # Plantilla de variables de entorno
```

## 🛠️ Tecnologías Utilizadas

### Backend & Core
- **Python 3.8+** - Lenguaje principal
- **BeautifulSoup4** - Web scraping
- **PyPDF2/pdfplumber** - Procesamiento de PDFs
- **Pandas** - Manipulación de datos
- **NumPy** - Computación científica

### Inteligencia Artificial
- **Google Generative AI (Gemini)** - Motor conversacional
- **SentenceTransformers** - Generación de embeddings
- **FAISS** - Búsqueda vectorial eficiente

### Gestión de Dependencias
- **Poetry** - Gestión moderna de dependencias
- **pip** - Instalador de paquetes Python

### Desarrollo
- **Jupyter Notebooks** - Experimentación y análisis
- **Git** - Control de versiones

## 📋 Requisitos del Sistema

### Requisitos Mínimos
- **Python**: 3.8 o superior
- **RAM**: 4GB mínimo, 8GB recomendado
- **Almacenamiento**: 2GB de espacio libre
- **Conexión a Internet**: Para descargas y API calls

### APIs Requeridas
- **Google Gemini API Key** - Para funcionalidad del chatbot
  - Obtén tu clave en: [Google AI Studio](https://makersuite.google.com/app/apikey)

## 🚀 Instalación y Configuración

### Opción 1: Instalación con Poetry (Recomendada)

```powershell
# 1. Clonar el repositorio
git clone https://github.com/tu-usuario/proyecto-examen.git
cd proyecto-examen

# 2. Instalar Poetry (si no está instalado)
curl -sSL https://install.python-poetry.org | python3 -

# 3. Instalar dependencias
poetry install

# 4. Activar el entorno virtual
poetry shell

# 5. Configurar variables de entorno
copy env.example .env
# Editar .env con tu API Key de Google Gemini
```

### Opción 2: Instalación con pip

```powershell
# 1. Clonar el repositorio
git clone https://github.com/tu-usuario/proyecto-examen.git
cd proyecto-examen

# 2. Crear entorno virtual
python -m venv .venv
.\.venv\Scripts\Activate.ps1

# 3. Actualizar pip
python -m pip install --upgrade pip

# 4. Instalar dependencias
pip install -r requirements.txt

# 5. Configurar variables de entorno
copy env.example .env
# Editar .env con tu API Key de Google Gemini
```

### ⚙️ Configuración de Variables de Entorno

Edita el archivo `.env` con la siguiente estructura:

```env
# Google Gemini API Configuration
GOOGLE_API_KEY=tu_api_key_aqui

# Optional: Custom configurations
PDF_DOWNLOAD_PATH=./data/pdfs
OUTPUT_PATH=./data/output
LOG_LEVEL=INFO
```

## 💻 Guía de Uso

### 🔄 Pipeline ETL Completo

Ejecuta el proceso completo de extracción, transformación y carga:

```powershell
# Ejecución básica
python main.py

# Con opciones avanzadas
python main.py --skip-download --skip-extraction --output-name mi_dataset
```

**Parámetros disponibles:**
- `--skip-download` - Omitir descarga de PDFs
- `--skip-extraction` - Saltar extracción de datos
- `--skip-embeddings` - No generar embeddings vectoriales
- `--pdf-dir <ruta>` - Directorio personalizado de PDFs
- `--output-name <prefijo>` - Prefijo para archivos de salida

### 🤖 MAC-GPT - Chatbot Inteligente

#### Interfaz de Consola
```powershell
# Iniciar chatbot en consola
python main.py --chatbot

# O directamente
python -m src.chatbot.cli
```

#### 🌐 Interfaz Web
```powershell
# Servidor web básico
python main.py --web

# Con configuración personalizada
python main.py --web --port 8080 --debug

# O directamente
python -m src.chatbot.web.run
```

La interfaz web estará disponible en: `http://localhost:5000`

### 💡 Uso Programático

```python
from src.chatbot import configure_google_api, ask_mac_gpt

# Configurar API
configure_google_api("TU_API_KEY")

# Realizar consulta
respuesta = ask_mac_gpt("¿Cuáles son las áreas de especialización de MAC?")
print(respuesta)
```

### ⚙️ Ejecución por Módulos

#### Solo Extracción
```powershell
python -m pipeline.extract \
    --pdf-dir ./data/pdfs \
    --output-name dataset_2024 \
    --skip-download
```

#### Solo Transformación
```powershell
python -m pipeline.transform \
    --input-file ./data/pickles/profesores.pkl \
    --output-format both \
    --text-columns nombre especialidad
```

## 📊 Ejemplos de Uso

### Consultas al Chatbot

```bash
# Preguntas sobre el plan de estudios
"¿Qué materias tiene el primer semestre de MAC?"

# Información sobre profesores
"¿Quién imparte la materia de Cálculo Diferencial?"

# Especialización
"¿Cuáles son las opciones de especialización en MAC?"
```

### Análisis de Datos

```python
import pandas as pd

# Cargar datos procesados
profesores = pd.read_csv('./data/csv/profesores.csv')
materias = pd.read_csv('./data/olap/olap_semestres_materias.csv')

# Análisis básico
print(f"Total de profesores: {len(profesores)}")
print(f"Materias por semestre: {materias.groupby('semestre').size()}")
```

## 🤝 Contribuir

¡Las contribuciones son bienvenidas! Aquí te explicamos cómo puedes participar:

### 🚀 Comenzar a Contribuir

1. **Fork** del repositorio
2. **Clona** tu fork localmente:
   ```powershell
   git clone https://github.com/tu-usuario/proyecto-examen.git
   ```
3. **Crea** una nueva rama para tu feature:
   ```powershell
   git checkout -b feature/nombre-descriptivo
   ```
4. **Realiza** tus cambios y commitea:
   ```powershell
   git commit -m "feat: descripción clara del cambio"
   ```
5. **Push** a tu rama:
   ```powershell
   git push origin feature/nombre-descriptivo
   ```
6. **Abre** un Pull Request

### 📝 Convenciones de Commits

Utilizamos [Conventional Commits](https://www.conventionalcommits.org/):

- `feat:` Nueva funcionalidad
- `fix:` Corrección de bugs
- `docs:` Cambios en documentación
- `style:` Cambios de formato (no afectan la lógica)
- `refactor:` Refactorización de código
- `test:` Añadir o modificar tests
- `chore:` Tareas de mantenimiento

### 🧪 Testing

Antes de enviar tu PR, asegúrate de que:
- [ ] El código sigue las convenciones de estilo de Python (PEP 8)
- [ ] Todas las funciones tienen docstrings
- [ ] Los tests pasan exitosamente
- [ ] Se mantiene la compatibilidad con Python 3.8+

## 📝 Licencia

Este proyecto está licenciado bajo la **Licencia MIT**. Esto significa que puedes usar, copiar, modificar y distribuir el código libremente, incluso para uso comercial, siempre que incluyas el aviso de copyright original.

Ver el archivo [LICENSE](LICENSE) para más detalles.

## 👥 Autores

### Desarrollador Principal
- **Elías Uriel Méndez Hernández** - [GitHub](https://github.com/eumendez) | [Email](mailto:eliasuriel_mh31@outlook.com)

### Institución
- **FES Acatlán - UNAM**
- **Carrera**: Matemáticas Aplicadas y Computación
- **Semestre**: 8vo

---

<div align="center">

**¿Te gusta este proyecto? ¡Dale una ⭐ en GitHub!**

[🐛 Reportar Bug](https://github.com/tu-usuario/proyecto-examen/issues) | [💡 Solicitar Feature](https://github.com/tu-usuario/proyecto-examen/issues) | [📖 Documentación](https://github.com/tu-usuario/proyecto-examen/wiki)

</div>