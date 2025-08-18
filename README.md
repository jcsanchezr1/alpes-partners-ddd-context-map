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

El flujo arranca con el descubrimiento y reclutamiento de afiliados; luego el manager hace onboarding/contrato, configura comisiones y condiciones de atribución y el monolito genera enlaces de tracking. El tag/pixel captura clics y el eCommerce reporta conversiones; el motor de atribución valida y produce reportes. Después, el motor de cálculo determina la comisión, Operaciones/Finanzas la aprueban, se dispara y emite el pago vía pasarela/banco y Tesorería concilia. Todo queda en modelos de lectura (lista de afiliados, reporte de clics/embudo, libro de comisiones, estado de pagos, conciliación).

El AS-IS muestra más elementos porque expone micro-pasos operativos del monolito y artefactos intermedios (p. ej., “planillas creadas”, “enlace generado”, “dashboard generado”) para evidenciar fricciones, dependencias y puntos de control.

### TO-BE
La imagen correspondiente al flujo de marketing de afiliados TO-BE se encuentra en la carpeta

  ```
  src/main/resources/
  ```
  Archivo:
  - `Event Storming - AlpesPartners TO-BE.jpg`

El Partner se registra (validación de duplicidad), la Marca crea el contrato, el equipo de marketing lanza la campaña y la plataforma reporta conversiones (S2S/pixel/API) como eventos que actualizan proyecciones. La Marca procesa el pago y se registra el pago procesado; el equipo de marketing genera reportes sobre modelos de lectura (detalle de partner, contrato, reporte de campaña, historial de pagos). Tracking/analytics y pagos quedan desacoplados como sistemas externos que publican/consumen eventos.

Se normaliza el lenguaje a eventos canónicos por dominio (registro de partner, contrato creado, campaña lanzada, conversión reportada, pago procesado) y se encapsulan validaciones como políticas dentro de cada bounded context o en sistemas externos desacoplados (tracking/analytics, pagos). Resultado: menos elementos visuales, misma o mayor capacidad, y menor acoplamiento con mejor escalabilidad.
