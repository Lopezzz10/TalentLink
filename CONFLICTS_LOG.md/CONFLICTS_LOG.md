# Registro de Conflictos - TalentLink

## Conflicto 1: Estilos del contenedor de destacados (display)
- **Fecha/Hora:** 04/07/2026 - 21:53
- **Archivos afectados:** `css/styles.css`
- **Ramas involucradas:** feature/css-jose (José) vs feature/css-alan (Alan)
- **Descripción del conflicto:** José aplicó `display: grid;` al `#contenedor-destacados` junto con `background-color: lightblue` en el body. Alan, en paralelo, aplicó `display: flex; flex-direction: column;` al mismo contenedor y cambió el fondo a `lightgreen`. Ambos cambios apuntaban a las mismas líneas del selector `#contenedor-destacados`, generando conflicto de merge.
- **Decisión tomada:** Se conservó `display: grid` (propuesta de José) por ofrecer mejor alineación de las tarjetas de oferta en pantallas grandes. Se descartó `flex-direction: column`. Respecto al color de fondo, se mantuvo `lightblue` como color oficial del proyecto.

## Conflicto 2: Cambio de selector CSS (ID a clase)
- **Fecha/Hora:** 04/07/2026 - 22:15
- **Archivos afectados:** `css/styles.css`, `index.html`
- **Ramas involucradas:** feature/css-evelyn (Evelyn)
- **Descripción del conflicto:** Evelyn renombró el selector `#contenedor-destacados` a `.destacados-container` en todo el archivo CSS, mientras que el HTML en `dev` todavía hacía referencia al `id="contenedor-destacados"`, generando inconsistencia entre estructura y estilos, además de conflicto de merge con los cambios de display de José y Alan.
- **Decisión tomada:** Se aprobó el cambio a clase (`.destacados-container`) por ser más flexible y reutilizable. Se actualizó `index.html` para usar `class="destacados-container"` en lugar del `id`, y se reaplicaron sobre esta clase los estilos de `display: grid` acordados en el Conflicto 1.

## Conflicto 3: Integración de las ofertas laborales en index.html
- **Fecha/Hora:** 04/07/2026 - 23:20
- **Archivos afectados:** `index.html`
- **Ramas involucradas:** feature/html-jose (Oferta A - José), feature/html-alan (Oferta B - Alan), rama de Evelyn (Oferta C)
- **Descripción del conflicto:** Los tres estudiantes agregaron sus respectivas tarjetas de oferta (Oferta A, Oferta B, Oferta C) dentro del mismo `<div class="destacados-container">`, insertando su código en la misma zona del archivo. Git no pudo fusionar automáticamente las tres inserciones simultáneas.
- **Decisión tomada:** Se conservaron las tres tarjetas de oferta, integrándolas en orden (Oferta A, Oferta B, Oferta C) dentro del contenedor, sin eliminar ninguna, ya que las tres cumplían con la funcionalidad del "Muro de Ofertas" y no se contradecían entre sí.

## Conflicto 4: Modificación del footer (información de contacto)
- **Fecha/Hora:** 04/07/2026 - 23:40
- **Archivos afectados:** `index.html`
- **Ramas involucradas:** rama de Evelyn
- **Descripción del conflicto:** Evelyn modificó la información de contacto del `<footer>` al mismo tiempo que se integraban las ofertas A y B en la misma sección del archivo, provocando un conflicto de líneas cercanas dentro de `index.html`.
- **Decisión tomada:** Se aceptó la actualización del footer propuesta por Evelyn (correo y teléfono de contacto actualizados), ya que no afectaba las tarjetas de oferta y mejoraba la información de contacto del portal.