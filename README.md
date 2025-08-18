# Alpes Partners DDD Context Map

## Estructura del Proyecto

- Los archivos `.cml` que definen los dominios, subdominios y los modelos de contexto (AS-IS y TO-BE) se encuentran en la ruta:
  ```
  src/main/cml/
  ```
  Archivos:
  - `alpes_domains.cml`
  - `alpes_contexts_asis.cml`
  - `alpes_contexts_tobe.cml`

- Las imágenes PNG generadas de los contextos se encuentran en:
  ```
  src/main/resources/
  ```
  - Imagen del contexto AS-IS: `src/main/resources/alpes_contexts_asis.png`
  - Imagen del contexto TO-BE: `src/main/resources/alpes_contexts_tobe.png`

- Las imágenes generadas automáticamente por Context Mapper (al usar la extensión) se almacenan en:
  ```
  src-gen/
  ```
 

## Requisitos y Herramientas de una de las maquinas que se trabajo.

- **Sistema operativo usado:** Ubuntu 24.04.2 LTS
- **Python:** 3.12.3
- **Java:** 17.0.15

- **IDE:** Visual Studio Code
  - Instalar la extensión "Context Mapper" desde el [Marketplace](https://marketplace.visualstudio.com/items?itemName=ContextMapper.context-mapper-vscode) o buscar "Context Mapper" en la vista de extensiones de VS Code.

- **Java JDK:** JDK 8 o superior (se recomienda JDK 15 GA por compatibilidad con VS Code).

- **Graphviz:** Necesario para generar imágenes gráficas del Context Map.
  - Descargar desde [https://www.graphviz.org/download/](https://www.graphviz.org/download/)
  - En Ubuntu, instalar con:
    ```sh
    sudo apt install graphviz
    ```

## Generación de Imágenes Context Map

1. Abrir el archivo `.cml` deseado (`alpes_contexts_asis.cml` o `alpes_contexts_tobe.cml`) en Visual Studio Code.
2. Hacer clic derecho sobre el archivo abierto y seleccionar **Generate Graphical Context Map**.
3. Elegir el formato de imagen (PNG o SVG) en la parte superior.
4. Hacer clic en **OK** para generar la imagen.
5. Las imágenes generadas se almacenan en la carpeta `src-gen/`.

## Referencia y Tutorial

- Se siguió el tutorial oficial: [https://misw4406.github.io/docs/semana_1/tutorial_2/](https://misw4406.github.io/docs/semana_1/tutorial_2/)
- El repositorio base usado para la práctica se encuentra en: [https://github.com/MISW4406-202310/Alpes-Context-Map](https://github.com/MISW4406-202310/Alpes-Context-Map)

## Lenguaje Ubicuo

### AS-IS

La imagen correspondiente al flujo de marketing de afiliados AS-IS se encuentra en la carpeta
  ```
  src/main/resources/
  ```
  Archivo:
  - `Event Storming - AlpesPartners AS IS.jpg`

### TO-BE
La imagen correspondiente al flujo de marketing de afiliados TO-BE se encuentra en la carpeta

  ```
  src/main/resources/
  ```
  Archivo:
  - `Event Storming - AlpesPartners TO-BE.jpg`
