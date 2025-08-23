<header>

# Using GitHub Copilot with Python

Bienvenido a un curso práctico y multi-módulo que transforma GitHub Copilot de una simple herramienta de autocompletado en tu programador AI proactivo de par. Ya sea que seas nuevo en la programación asistida por IA o que busques profundizar tu experiencia, en este módulo aprenderás cómo aprovechar las características de Copilot y mejorar tu eficiencia al programar en Python. Obtendrás una comprensión clara de las capacidades principales de Copilot y cómo se integran en los flujos de trabajo modernos de Python. Esta es una experiencia práctica para comprender las sugerencias en línea, el prompting en lenguaje natural y las sugerencias de código conscientes del contexto.

¡Prepárate para abordar un proyecto práctico y poner manos a la obra! Trabajarás en la modificación de un repositorio de Python para construir un formulario HTML interactivo y un endpoint de API. Este proyecto práctico te proporcionará una experiencia valiosa en la creación de una aplicación web de Python que sirve una API HTTP y genera tokens pseudo-aleatorios para propósitos de identificación.

</header>


- **¿Para quién es este curso?**: Desarrolladores, Ingenieros DevOps, Gerentes de desarrollo de software, Testers.
- **¿Qué aprenderás?**: Cómo usar GitHub Copilot para completacion de código, sugerencias "inline" y sugerencias de siguiente edición, así como agregar comentarios a tu trabajo.
- **¿Qué construirás?**: Archivos de Python que tendrán código generado por Copilot AI para sugerencias de código y comentarios.
- **Prerrequisitos**: GitHub Copilot está disponible para usar gratis, regístrate en [GitHub Copilot](https://gh.io/copilot).
- **Tiempo**: Este módulo se puede completar en menos de una hora.

Al final de este módulo, adquirirás las habilidades para poder:

- Interactuar con Copilot en el IDE usando sugerencias en línea y finalizaciones de siguiente edición. 
- Crear prompts para generar sugerencias de GitHub Copilot usando finalización de código y chat.
- Aplicar GitHub Copilot para mejorar tus proyectos.

## Lectura previa:
- [Introducción a la ingeniería de prompts con GitHub Copilot](https://learn.microsoft.com/training/modules/introduction-prompt-engineering-with-github-copilot//?WT.mc_id=academic-113596-abartolo)
- [Usando GitHub Copilot con Python](https://learn.microsoft.com/en-us/training/modules/introduction-copilot-python/?WT.mc_id=academic-113596-abartolo)

## Requirements

1. Habilita tu [servicio de GitHub Copilot](https://github.com/github-copilot/signup)
   
2. Abre [este repositorio con Codespaces](https://codespaces.new/MicrosoftDocs/mslearn-copilot-codespaces-python)

## 💪🏽 Exercise

**Haz clic derecho en el siguiente botón de Codespaces para abrir tu Codespace en una nueva pestaña**
 
[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/MicrosoftDocs/mslearn-copilot-codespaces-python)

La API ya tiene un endpoint único para generar un token. Vamos a actualizar la API agregando un nuevo endpoint que acepte texto y devuelva una lista de tokens.

### 🗒️ Section 1: Explorando Su Proyecto

🎯**Objetivos de Aprendizaje**
- Usar la completacion de código en línea para crear nuevas clases y métodos
- Activar y refinar las completacioness de Copilot
- Usar chat en línea y comandos de barra
  
Una vez que tu Codespace se inicie, tendrás un entorno de desarrollo completamente funcional con todo el repositorio precargado. Este es el momento perfecto para explorar GitHub Copilot Chat para ayudarte a entender mejor la base de código.

Para comenzar:

1. Haz clic en el icono de Copilot Chat en la esquina superior derecha de la ventana de Codespace:

<div align="left">
<img src="../../../Using-GitHub-Copilot-with-Python/images/001Chat.jpg" alt="Open GitHub Copilot Chat">
</div>

2. En lugar de explorar manualmente el proyecto y varias carpetas, intenta pedirle a Copilot una vista general. En el panel de chat, escribe '/' para ver los comandos de barra disponibles — estos ofrecen formas rápidas y estructuradas de interactuar con Copilot.

   Escribe `/help` para ver todos los comandos, o consulta la [hoja de trucos de GitHub Copilot Chat](https://docs.github.com/copilot/reference/github-copilot-chat-cheat-sheet#slash-commands) para una lista de comandos de barra disponibles.

   Por ejemplo, puedes usar:
   - `/doc` para agregar un comentario de documentación
   - `/explain` para explicar el código
   - `/fix` para proponer una solución a los problemas en el código seleccionado
   - `/generate` para generar código que responda tu pregunta

3. En lugar de usar lenguaje natural, escribe `/explain` en el panel de chat. La salida de GitHub Copilot irá a los detalles de cómo está estructurado el proyecto, incluyendo información adicional sobre los detalles del Frontend y Backend.

<div align="left">
<img src="../../../Using-GitHub-Copilot-with-Python/images/002explain.gif" alt="Output of /Explain">
</div>

4. Como aprendiz visual, puedes pedirle a GitHub Copilot que 'cree un diagrama del flujo de trabajo de la aplicación'. Esto podría guardarse en un README para documentación adicional.

<div align="left">
<img src="../../../Using-GitHub-Copilot-with-Python/images/003diagramoutput.gif" alt="Output of Mermaid syntax">
</div>

En los ejercicios anteriores logramos lo siguiente: 
- ✅ Usamos comandos de barra para explicar código nuevo
- ✅ Creamos un diagrama para visualizar y entender el flujo de la aplicación
  
### 🗒️ Section 2: Completacion de Código

**🎯 Objetivos de Aprendizaje**

- Usar la completacion de código en línea para escribir código desde comentarios.
- Activar y refinar las finalizaciones de Copilot.
- Usar chat en línea y comandos de barra.

En la sección anterior aprendiste cómo usar tanto lenguaje natural como comandos de barra para entender rápidamente la base de código sin revisar carpetas. En el siguiente conjunto de ejercicios vamos a usar Copilot para agregar un modelo `Pydantic` y generar un nuevo endpoint. 

1. Abre el panel de archivos y navega a `webapp/main.py`. Abre el archivo `main.py`, navega al final de los archivos y escribe (o copia):

```python
# Create a Pydantic model so that I can use it in a new route that will accept JSON with text as a key which accepts a string
```

La salida debería ser similar a esta: 

<div align="left">
<img src="../../../Using-GitHub-Copilot-with-Python/images/004pydanticmodel.jpg" alt="Create a Pydantic model">
</div>

2. Ahora queremos usar la característica "inline" de Copilot. Cuando usamos la característica "inline" podemos enfocarnos en el código frente a nosotros y hacer cambios progresivos en nuestra base de código. A continuación, vamos a generar un nuevo endpoint en la parte inferior del archivo `main.py`. Coloca tu cursor debajo de la última ruta que se creó y presiona `CTRL + I` para abrir el chat en línea. Escribe o copia el siguiente texto: 

```python
# Create a FastAPI endpoint that accepts a POST request with a JSON body containing a single field called "text" and returns a checksum of the text 
```

<div align="left">
<img src="../../../Using-GitHub-Copilot-with-Python/images/005inlinefastapi.gif" alt="Copilt Chat Inline">
</div>

3. Acepta la sugerencia y resalta el bloque de texto que Copilot ha generado. Abre la ventana de prompt en línea nuevamente (`CRTL + I`) y escribe:

```python
/improve 
```

<div align="left">
<img src="../../../Using-GitHub-Copilot-with-Python/images/006improvechecksum.gif" alt="Improve Checksum">
</div>

Revisa las sugerencias de Copilot y verifica la salida. En este caso combinamos tanto la capacidad de comandos de barra como la característica de chat "inline". **Nota:** Es importante siempre verificar la salida de Copilot.

5. Después de generar el código del endpoint `/checksum`, puedes explorar un poco más con Copilot. Prueba las siguientes sugerencias: 

```python
Enhance the checksum endpoint to accept a 'hash_type' parameter that can be 'md5', 'sha1', or 'sha256'
```

```python
Add validation to ensure text is not empty and has a maximum length of 1000 characters
```

```python
Improve the docstring for the checksum_text function with more details and examples
```

7. Mientras que las sugerencias "inline" son excelentes para sugerir código similar a un mecanismo de autocompletado, las Sugerencias de Siguiente Edición (NES) predicen el siguiente cambio lógico en tu código basándose en ediciones recientes en cualquier parte de tu archivo. Esto ayuda a mantener el flujo y la consistencia como desarrollador. NES sugiere revisiones a tu código, comentarios e incluso pruebas. Puede rastrear cambios recientes para anticipar ediciones futuras, trabajando a través de múltiples líneas y símbolos. Resaltará las sugerencias con flechas en la canaleta del editor. En los pasos anteriores ya habrás notado una flecha verde en la canaleta, proporcionando una sugerencia y la capacidad de aceptar o rechazar la sugerencia. 

**Nota:** En el caso de que no veas que aparezcan [Sugerencias de Siguiente Edición](https://code.visualstudio.com/blogs/2025/02/12/next-edit-suggestions) en tu editor, verifica que estén habilitadas en tu editor. 

<div align="left">
<img src="../../../Using-GitHub-Copilot-with-Python/images/007nexteditpython.jpg" alt="Next Edits">
</div>

En los ejercicios anteriores logramos lo siguiente: 
- ✅ Generamos sugerencias desde comentarios de código
- ✅ Usamos chat en línea para generar código nuevo, consultar código y aceptar sugerencias de codificación
- ✅ Activamos y refinamos sugerencias de Copilot

### 📄Section 3: GitHub Copilot en Modo Agente

🎯**Objetivos de Aprendizaje**
- Observar codificación autónoma y generación de PR (Pull Request)
- Asignar issues al agente de codificación de Copilot

[GitHub Copilot Agent Mode](https://github.blog/ai-and-ml/github-copilot/agent-mode-101-all-about-github-copilots-powerful-mode/) es un asistente de codificación AI autónomo que actúa como un colaborador sincrónico en tiempo real. Puede realizar tareas de codificación que requieren múltiples pasos mientras usa tus prompts en lenguaje natural. Cuando trabajas en Agent Mode, Copilot puede resolver problemas junto contigo, entendiendo tu intención, y cuando la solución construida necesita algunos ajustes, puede iterar hasta que lo haga bien. En esta sección vamos a usar Agent Mode para hacer una multitud de cambios a nuestro servicio backend para proporcionar varias mejoras a nuestro código. 

1. Abre GitHub Copilot Chat. Nota que en el cuadro de texto puedes 'agregar contexto', lo que te permite adjuntar archivos, carpetas y otros elementos al contexto de Copilot para que pueda entender mejor tu base de código. El modo agente debería estar seleccionado por defecto. También tienes la capacidad de elegir tu modelo. También nota que la pestaña abierta `main.py` está siendo referenciada para contexto. 

<div align="left">
<img src="../../../Using-GitHub-Copilot-with-Python/images/008agentmodechat.jpg" alt="Agent Mode Chat" >
</div>

2. Dale al modo agente un prompt detallado. Para este ejemplo vamos a pedirle a Copilot que haga varias mejoras a nuestro proyecto. Copia y pega el prompt de abajo en la ventana de Chat.

```
1.	Fix and resolve all code structure issues, including using proper Python comments and syntax
2.	Improve the API design to include consistent error handling, input validation and API versioning.
3.	Include unit and integration tests and ensure everything in this project is well documented. 
4.	Make this application deployment ready 
5.	Improve the performance and security of this application.
```

Cuando se ejecuta en modo agente, Copilot tomará un poco más de tiempo para trabajar a través de todas las tareas. Primero analizará tu intención desde el prompt de arriba. Planificará y ejecutará las varias tareas. 

<div align="left">
<img src="../../../Using-GitHub-Copilot-with-Python/images/009agentmodeplanpython.jpg" alt="Output Agent Mode Implementation">
</div>

Pero donde el modo agente realmente brilla es que iterará en su propia salida hasta que resuelva errores y alcance una solución funcional. Mientras el modo agente está ejecutándose, podemos ver que está ejecutando pruebas para verificar y validar su propio código:

<div align="left">
<img src="../../../Using-GitHub-Copilot-with-Python/images/010agentmodetestspy.gif" alt="Output Agent Mode Tests">
</div>

Mientras Agent Mode está trabajando, también podemos ver que ha creado documentación según nuestros requisitos esbozados en las tareas que se le dieron: 

Para este paso en el taller, el modo agente debería haber tomado varios minutos para completar tus tareas. Revisa los varios cambios y confirma que han logrado toda la salida dada. Con Agent mode, también genera qué cambios se hicieron. El siguiente resumen de cambios que se hicieron está resumido abajo:

```md
**Code Structure Issues Fixed**
- Replaced JavaScript-style single-line comments (//) with proper Python comments (#)
- Fixed indentation issues in the checksum endpoint
- Restructured the application into proper modules and packages
- Followed PEP 8 style guidelines

**API Design Improvements**
- Added API versioning with a /api/v1 prefix
- Implemented consistent error handling with try/except blocks
- Enhanced input validation using Pydantic's Field and validator capabilities
- Added response models for type checking and documentation
- Added health check endpoint for monitoring

**Tests and Documentation**
- Created comprehensive unit tests for utility functions
- Added integration tests for API endpoints
- Improved docstrings in all functions and classes
- Created a detailed README with examples and instructions

**Deployment Ready**
- Added a Dockerfile for containerization
- Created a gunicorn configuration for production deployment
- Added a run script for local development
- Enhanced the requirements.txt file with specific versions

**Performance and Security Enhancements**
- Added GZIP compression middleware for better performance
- Implemented rate limiting headers
- Added CORS middleware with configurable origins
- Improved error handling to prevent information leakage
- Added logging for better monitoring and debugging
- Implemented more flexible hashing algorithms with proper validation
- The application now follows best practices for Python web applications, with a clear structure, proper error handling, comprehensive testing, and deployment configuration.
```

3. Finalmente, verifica que los cambios y el nuevo endpoint estén funcionando. Copilot generará el endpoint para ti, o puedes navegar al panel 'ports' en la ventana de terminal para obtener la URL. La URL debería tener el siguiente formato: 

```bash
https://< your codespace url >.app.github.dev
```

<div align="left">
<img src="../../../Using-GitHub-Copilot-with-Python/images/011endpoint.jpg" alt="Endpoint URL">
</div>

🚀¡Felicitaciones! Ahora entiendes el poder detrás del Agent Mode y las muchas tareas con las que puede ayudar. Desplázate hacia abajo a la siguiente sección que te mostrará cómo agregar contexto y personalización a Copilot. 

Agent Mode pudo realizar tareas específicas de Python:
- ✅ Resolvió problemas de estructura de código
- ✅ Mejoras al diseño de la API
- ✅ Creó pruebas y documentación
- ✅ Creó una aplicación lista para despliegue
- ✅ Mejoró el rendimiento y proporcionó mejoras de seguridad

### 🗒️ Section 4: Personalización y Contexto 

🎯 Objetivos de Aprendizaje
- Entender las diferentes formas de personalizar GitHub Copilot y recibir mejores respuestas de los prompts.
- Entender el rol del Model Context Protocol (MCP).

**Parte 1: Instrucciones Personalizadas**

Los archivos de instrucciones de GitHub Copilot son documentos markdown que proporcionan contexto esencial para guiar el comportamiento de Copilot dentro de una base de código específica. Estos archivos ayudan a adaptar las sugerencias generadas por AI para que coincidan con los estándares de codificación de tu equipo, patrones arquitectónicos, convenciones de nomenclatura, estrategias de testing y prácticas de despliegue. Hay dos tipos de archivos de instrucciones: instrucciones globales, que se aplican a todo el repositorio y se almacenan en `copilot-instructions.md`, e instrucciones de alcance, que se aplican solo a archivos o carpetas específicos y se colocan en `.github/instructions/*instructions.md`.

Al proporcionar a Copilot contexto detallado del proyecto, los archivos de instrucciones mejoran significativamente la relevancia y precisión de sus sugerencias de código. Por ejemplo, si tu proyecto usa Django, FastAPI, o Flask, Copilot puede generar componentes que sigan tu estructura preferida, usen características modernas de Python, y se adhieran a tus convenciones de nomenclatura. Esto lleva a código más consistente y reduce la necesidad de correcciones manuales o revisiones de código extensas. Los archivos de instrucciones también mejoran la capacidad de Copilot para generar pruebas y documentación significativas. Con el contexto correcto, Copilot puede sugerir pruebas unitarias usando unittest o pytest, pruebas de integración con herramientas como requests o httpx, e incluso agregar docstrings o anotaciones OpenAPI a tus endpoints de FastAPI o Flask. Al refactorizar o agregar nuevas características, Copilot respeta tu configuración de inyección de dependencias, patrones de configuración y estrategias de manejo de errores, haciéndolo un asistente más inteligente y confiable.

Más allá de los beneficios técnicos, los archivos de instrucciones mejoran la colaboración entre equipos. Los nuevos contribuyentes pueden confiar en Copilot para guiarlos a través de bases de código desconocidas, asegurando que sigan las prácticas establecidas sin necesidad de incorporación extensa. Esto hace que los archivos de instrucciones sean una herramienta poderosa para mantener la calidad del código, agilizar los flujos de trabajo de desarrollo y fomentar la alineación del equipo.

Por ejemplo, en tu proyecto puedes definir el estilo de codificación (como PEP 8, type hints, y formatos de docstring), estrategias de testing (frameworks, mocking, y convenciones de nomenclatura), y preferencias de herramientas (como linters, formatters, y package managers). También ayudan a alinear Copilot con la arquitectura de tu proyecto, patrones de diseño, y prácticas específicas del framework (ej., Django, FastAPI), mientras guían estándares de documentación como comentarios "inline" y docstrings.

¡Creemos nuestro primer archivo de instrucciones personalizadas global!

1. Crea un archivo `copilot-instructions.md` en el directorio `.github`: 

<div align="left">
<img src="../../../Using-GitHub-Copilot-with-Python/images/012instructionpy.jpg" alt="Instructions File Location" width="500" height="700" >
</div>

El ejemplo de abajo puede ser personalizado en tu propio proyecto, para este ejemplo hemos creado un archivo de instrucciones específico a nuestros requisitos de Python en este proyecto. 

```md
# Project Guidelines

## Project Overview

This repository contains a FastAPI application that provides various endpoints for token generation, text echo, and checksum calculation. 

## Technology Stack
-  **Token Generation** - An endpoint that generates secure random tokens with configurable length.
- **Text Echo** - A simple endpoint that echoes back any text sent to it.
- **Checksum Calculation** - An endpoint that calculates cryptographic hashes (SHA-256, SHA-512, or MD5) for provided text.
- **Health Checking** - A monitoring endpoint that returns the API status and version.

### ✨ Coding Style
- Follow **PEP 8** standards for formatting and naming.
- Use **type hints** consistently across all functions.
- Prefer **f-strings** for string interpolation.
- Include **Google-style docstrings** for all public functions and classes.

### 🧪 Testing Guidance
- Use **pytest** for writing unit tests.
- Mock external dependencies using `pytest-mock`.
- Name tests descriptively, e.g., `test_generate_token_valid_input`.

### 🏗️ Architecture Preferences
- Use **FastAPI** conventions for routing and dependency injection.
- Define **Pydantic models** for request and response schemas.
- Keep logic modular—separate API routes, models, and utility functions.

### 📚 Documentation & Comments
- Generate concise inline comments for non-obvious logic.
- Include endpoint descriptions in FastAPI route docstrings.
- Avoid redundant comments that restate code behavior.
```

2. También puedes crear archivos de instrucciones específicos que se aplicarán automáticamente solo a archivos o directorios específicos. Deben estar dentro de un directorio `.github/instructions` y terminar en `.instructions.md`. 

En el directorio `.github`, crea un subdirectorio `instructions`. Dentro del subdirectorio, crea un archivo `APIroutes.instructions.md`. Vamos a usar los requisitos existentes para los endpoints de la API en nuestro proyecto:

```md
---
applyTo: "webapp/api/*.py"
---

## Coding Conventions

- Follow PEP 8 for variables and functions
- PascalCase for class names
- Use typehints for clarity and tooling support 
- Add detailed docstrings to endpoint functions
- Include examples in Pydantic model Config
- Use descriptive parameter names and Field descriptions
- Consider async handlers for I/O bound operations
- Configure CORS with specific origins in production
- Use middleware for rate limiting


## Accessibility

- Ensure proper contrast ratios for text
- Provide human-readable error messages with actionable information
```

3. Adjunta tu archivo de instrucciones recién creado a GitHub Copilot Chat en Agent Mode y referencia el cambio en la salida de los ejemplos anteriores.

En los ejercicios anteriores logramos lo siguiente: 
- ✅ Creamos y aplicamos archivos de instrucciones de alcance global
- ✅ Entendimos cómo Copilot interpreta y sigue estas reglas
- ✅ Usamos archivos de instrucciones para hacer cumplir estándares del equipo y reducir sobrecarga
- ✅ Confiadamente solicitamos a Copilot código consistente y de alta calidad


**Parte 2: Model Context Protocol (MCP)**

Model Context Protocol (MCP) es un estándar universal que permite a las herramientas de AI integrarse e interactuar con servicios externos. Un host MCP puede conectarse a uno o más servidores MCP, que a su vez proporcionan herramientas que una herramienta de AI puede utilizar. 

El modo agente de GitHub Copilot soporta MCP, por lo que puedes conectarte a miles de servicios. Microsoft proporciona muchos servidores MCP, incluyendo unos para GitHub, Azure AI Foundry, y Playwright. No son solo para obtener datos, sino que pueden realizar operaciones complejas con lenguaje natural y Copilot. 

Puedes aprender más sobre MCP y cómo configurarlo usando el curso dedicado de [GitHub Skills Integration MCP with GitHub Copilot](https://github.com/skills/integrate-mcp-with-copilot).

### Enlaces Útiles y Aprendizaje Adicional
- [Usar modo agente en VS Code](https://code.visualstudio.com/docs/copilot/chat/chat-agent-mode)
- [Hoja de trucos de GitHub Copilot Chat](https://docs.github.com/copilot/reference/github-copilot-chat-cheat-sheet)
- [Instrucciones personalizadas](https://docs.github.com/copilot/how-tos/configure-custom-instructions/add-repository-instructions)

## Avisos Legales

Microsoft y cualquier contribuyente te otorgan una licencia para la documentación de Microsoft y otro contenido
en este repositorio bajo la [Licencia Pública Internacional Creative Commons Attribution 4.0](https://creativecommons.org/licenses/by/4.0/legalcode),
ver el archivo [LICENSE](LICENSE), y te otorgan una licencia para cualquier código en el repositorio bajo la [Licencia MIT](https://opensource.org/licenses/MIT), ver el
archivo [LICENSE-CODE](LICENSE-CODE).

Microsoft, Windows, Microsoft Azure y/o otros productos y servicios de Microsoft referenciados en la documentación
pueden ser marcas comerciales o marcas comerciales registradas de Microsoft en los Estados Unidos y/o otros países.
Las licencias para este proyecto no te otorgan derechos para usar nombres, logos o marcas comerciales de Microsoft.
Las pautas generales de marcas comerciales de Microsoft se pueden encontrar en http://go.microsoft.com/fwlink/?LinkID=254653.

La información de privacidad se puede encontrar en https://privacy.microsoft.com/en-us/

Microsoft y cualquier contribuyente se reservan todos los demás derechos, ya sea bajo sus respectivos derechos de autor, patentes,
o marcas comerciales, ya sea por implicación, estoppel o de otra manera.
---

## �� Nota de Traducción

Este documento fue traducido del inglés al español utilizando **GitHub Copilot** como herramienta de asistencia, y **supervisado y revisado** por un traductor humano para garantizar precisión y claridad educativa.

*La traducción mantiene todos los enlaces, código y referencias técnicas del documento original.*

---