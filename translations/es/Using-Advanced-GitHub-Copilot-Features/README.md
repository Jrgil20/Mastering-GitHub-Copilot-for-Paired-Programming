<header>

# Uso de Funciones Avanzadas de GitHub Copilot

GitHub Copilot ofrece mucho más que simples sugerencias de código. Como Ingeniero de Software, a menudo necesitas entender el código existente y mejorarlo con documentación, pruebas y automatización.

En este módulo, explorarás las funciones avanzadas de GitHub Copilot, permitiéndote trabajar de manera interactiva con tu código mientras aplicas sugerencias e ideas de manera más efectiva.

Usando una API HTTP basada en Python, realizarás modificaciones, corregirás errores, crearás documentación y escribirás pruebas para un nuevo endpoint que implementarás.
</header>


- **Para quién es esto**: Desarrolladores, Ingenieros de DevOps, Gerentes de desarrollo de software, Testers.
- **Lo que aprenderás**: Uso de funciones avanzadas de GitHub Copilot para probar, documentar y trabajar con código.
- **Lo que construirás**: Una nueva ruta de API HTTP, junto con documentación y pruebas para verificar su corrección.
- **Prerrequisitos**: GitHub Copilot está disponible para usar de forma gratuita, regístrate en [GitHub Copilot](https://gh.io/copilot).
- **Tiempo**: Este módulo se puede completar en menos de una hora.

Al final de este módulo, adquirirás las habilidades para poder:

- Usar funciones avanzadas de GitHub Copilot como chat en línea, comandos de barra diagonal y agentes.
- Interactuar con GitHub Copilot con un contexto más profundo sobre tu proyecto y hacer preguntas al respecto.

## Lectura previa requerida:
- [Introducción a la ingeniería de prompts con GitHub Copilot](https://learn.microsoft.com/training/modules/introduction-prompt-engineering-with-github-copilot//?WT.mc_id=academic-113596-abartolo)
- [Uso de funciones avanzadas de GitHub Copilot](https://learn.microsoft.com/training/modules/advanced-github-copilot/?WT.mc_id=academic-113596-abartolo)

## Requisitos

1. Habilita tu [servicio de GitHub Copilot](https://github.com/github-copilot/signup)
1. Abre [este repositorio con Codespaces](https://codespaces.new/MicrosoftDocs/mslearn-advanced-copilot)

## 💪🏽 Ejercicio

**Haz clic derecho en el siguiente botón de Codespaces para abrir tu Codespace en una nueva pestaña**
 
[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/MicrosoftDocs/mslearn-copilot-codespaces-python)

La API actual no está exponiendo country/{country} que necesita ser implementada para listar ciudades. La ruta debe permitir solo solicitudes HTTP GET con una respuesta JSON que proporcione información de los máximos y mínimos históricos para ese país, ciudad y mes dado.

Como con cualquier implementación, esta adición debe incluir al menos una función de prueba para trabajar con el ejecutor pytest y el marco de pruebas. 

### 🛠 Paso 1: Agregar una nueva ruta 
En nuestro primer ejercicio crearemos una nueva ruta en nuestra API. Ve al archivo main.py, y usando el chat en línea con el siguiente comando `ctrl` + `i` (en Windows) o `cmd` + `i` (en Mac) pide a GitHub Copilot que te ayude a crear una nueva API que te muestre las ciudades de un país.

Usa el siguiente prompt en el chat en línea:

```
Create a new route that exposes the cities of a country.
```

Este prompt debería darte algo similar a esto:


```python
# Create a new route that exposes the cities of a country:
@app.get('/countries/{country}')
def cities(country: str):
    return list(data[country].keys())

```

> [!NOTE]
> Prueba tu nueva ruta y refina tu prompt hasta que el resultado sea el deseado.

### 🔎 Paso 2: Crear una prueba
Ahora que has creado una nueva ruta, creemos una prueba con Copilot Chat para esta ruta que use España como país. Recuerda seleccionar tu código y pedir a Copilot Chat que te ayude con esta API específica que acabamos de crear.

Usa el siguiente prompt con GitHub Copilot Chat:

```
/tests help me to create a new test for this route that uses Spain as the country.
```

![Copilot Chat image example](https://raw.githubusercontent.com/MicrosoftDocs/mslearn-advanced-copilot/main/images/ideascopilot.png)


Una vez que Copilot te haya ayudado a crear tu prueba, pruébala. Si no está funcionando como se esperaba, no dudes en compartir esos detalles con Copilot en el chat. Por ejemplo:

```
This test is not quite right, it is not including cities that doesn't exist. Only Seville is part of the API.
```

Debería darte otra solución. Sigue intentando hasta que logres el resultado deseado.

### 🐍 Paso 3: Usar un agente para escribir el proyecto
Durante este paso usaremos un agente (workspace) para escribir la documentación del proyecto sobre cómo ejecutar este proyecto. En el GitHub Copilot Chat, probaremos el siguiente prompt:

`> @workspace help me to use an agent to write the project documentation on how to run it .`

Finalmente, verifica que el nuevo endpoint esté funcionando probándolo yendo al endpoint `/docs` y confirmando que el endpoint aparezca.


### 💡 Paso 4: Usando Comandos de Barra Diagonal

Ahora que has usado GitHub Copilot para generar y explicar código, también puedes explorar algunos otros enfoques alternativos para realizar tareas de desarrollador. Estos desafíos adicionales te ayudarán a profundizar en otras funciones de GitHub Copilot además de las que ya conoces. Para estos desafíos adicionales, usarás la interfaz de Chat. Haz clic en el icono de GitHub Copilot Chat en la barra lateral izquierda si no lo tienes abierto todavía.

🚀 Felicitaciones, a través del ejercicio, has usado GitHub Copilot con muchas funciones diferentes que te permitirán trabajar mejor con diferentes proyectos. Has usado de manera interactiva algunas funciones para escribir pruebas, documentación y descubrir más sobre el código existente.

## Avisos Legales

Microsoft y cualquier contribuyente te otorgan una licencia para la documentación de Microsoft y otro contenido
en este repositorio bajo la [Licencia Pública Internacional Creative Commons Attribution 4.0](https://creativecommons.org/licenses/by/4.0/legalcode),
consulta el archivo [LICENSE](LICENSE), y te otorgan una licencia para cualquier código en el repositorio bajo la [Licencia MIT](https://opensource.org/licenses/MIT), consulta el
archivo [LICENSE-CODE](LICENSE-CODE).

Microsoft, Windows, Microsoft Azure y/o otros productos y servicios de Microsoft referenciados en la documentación
pueden ser marcas comerciales o marcas comerciales registradas de Microsoft en Estados Unidos y/o otros países.
Las licencias para este proyecto no te otorgan derechos para usar nombres, logotipos o marcas comerciales de Microsoft.
Las pautas generales de marcas comerciales de Microsoft se pueden encontrar en http://go.microsoft.com/fwlink/?LinkID=254653.

La información de privacidad se puede encontrar en https://privacy.microsoft.com/en-us/

Microsoft y cualquier contribuyente se reservan todos los demás derechos, ya sea bajo sus respectivos derechos de autor, patentes,
o marcas comerciales, ya sea por implicación, impedimento o de otro modo.
