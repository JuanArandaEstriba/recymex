# RECYMEX® · Presentación para llamada comercial

Deck web de **12 láminas** para la llamada de 15–20 min que sigue al primer contacto por
WhatsApp. Objetivo único: **vender uno de los tres servicios** y salir con la información
para cotizar.

Un solo archivo (`index.html`), autocontenido: Barlow + Inter empotradas en base64, logos
embebidos, **cero referencias externas**. Se abre en cualquier navegador, con o sin internet.

**Link:** https://juanarandaestriba.github.io/recymex/

## Cómo se presenta

- **Escritorio:** flechas ← →, barra espaciadora, o clic en los costados.
- **Celular:** swipe.
- **Puntos abajo:** salto a cualquier lámina. Contador abajo a la derecha.
- **Ramificado:** en la lámina 04 le picas al servicio que aplica y salta directo. Cada
  lámina de servicio trae **← SERVICIOS** para volver. O sigues con la flecha y ves los tres.

Para Zoom/Meet: abre el link, F11 y comparte pantalla.

## Recorrido (12 láminas · 10 por llamada con ramificación)

| # | Lámina | Qué dice |
|---|---|---|
| 01 | Portada | Soluciones integrales en manejo y destrucción de residuos en México |
| 02 | Qué hacemos | Una solución integral, de principio a fin: certeza jurídica, certeza financiera, un solo responsable |
| 03 | Con qué respaldo | Autorizaciones, permisos y equipo propio + los cuatro números |
| 04 | **¿Cuál es tu caso?** | Hub ramificado, con glifo animado por servicio |
| 05 | Destrucción fiscal | Liberas almacén, lo sacas de libros, lo deduces. Acompañamiento legal |
| 06 | Residuos IMMEX | Estudio previo de factibilidad y viabilidad + equipo de comercio exterior |
| 07 | Gestión de residuos | Permisos en regla, la frecuencia que necesites, app de seguimiento |
| 08 | Cómo trabajamos | Las tres etapas |
| 09 | Nuestros expedientes | Qué te entregamos |
| 10 | Cobertura | Operamos en todo el país |
| 11 | Cotización | Cada proyecto es distinto. La información que necesitamos, en formato de formulario |
| 12 | Siguientes pasos | Tú / Nosotros + contacto |

## Reglas de redacción de este deck

Se aplican a todas las láminas y conviene respetarlas al editar:

1. **Poco texto.** Se presenta en vivo, no se lee. Máximo ~40 palabras de cuerpo por lámina.
2. **Títulos planos.** Nada de ingenio ni juegos de palabras. Que digan lo que la lámina dice.
3. **Ningún servicio se compara contra otro.** Cada lámina de servicio habla solo de sí misma.
   Nunca "aquí no hay trámite fiscal" o "esto es más rápido que".
4. **No se compromete ningún tiempo** salvo uno: la cotización toma **5 a 15 días** *una vez
   que la información está completa*. Nada sobre cuánto tarda conseguir la información,
   ni cuánto tarda un proyecto.
5. **Cada servicio vende su ventaja real**, no una descripción genérica:
   - Destrucción fiscal → nos encargamos de todo, **acompañamiento legal** hasta la
     declaración anual, expediente de hasta 400 hojas, y **lo deduces**
   - Residuos IMMEX → **estudio previo de factibilidad y viabilidad con sustento jurídico**
     (primero se dictamina, después se ejecuta) y el **equipo de comercio exterior**
   - Gestión de residuos → **todos los permisos**, la frecuencia que necesites, y la
     **app de seguimiento**
6. **Sin nombres de presentador**, para que la pueda dar cualquiera del equipo.
7. **No se nombra a ningún cliente.**

## Layout de las láminas de servicio

Las láminas con tres tarjetas (02, 05, 06, 07, 10) usan esta estructura, de arriba abajo:

1. **Título** a lo ancho, arriba.
2. **Columna izquierda:** la frase protagonista y debajo las tres tarjetas apiladas
   (verticales, con el título grande en negritas).
3. **Columna derecha:** la ilustración, **centrada verticalmente**.

## Fotografía

Cinco fotos reales empotradas en base64, optimizadas a 1280 px (52% de calidad para las de
fondo, que van bajo un velo oscuro; 1500 px al 86% para la captura de la app):

| Lámina | Foto | Cómo entra |
|---|---|---|
| 01 Portada | Proceso en planta | Fondo completo con velo oscuro |
| 08 Antes/durante/después | Recolección en el andén del cliente | Fondo completo (esta lámina pasó de verde a oscura) |
| 09 Nuestros expedientes | Captura del acta en la plataforma | Enmarcada, en la columna derecha |
| 11 Queremos saber de ustedes | Almacén del cliente con inventario | Fondo completo |
| 12 Cierre | Equipo operando | Fondo completo |

Los originales quedan en `fotos/`, las versiones optimizadas en `fotos/opt/`.
Para cambiar una foto: reemplaza el archivo en `fotos/`, corre el optimizador y vuelve a
embeber (ver el commit correspondiente para el script).

## Ilustraciones

Librería de animaciones propia (no genérica), cada una es el *verbo* de su lámina:

- **02** — las tres corrientes convergen en RECYMEX y salen como valor recuperado + expediente
- **04** — un glifo animado por servicio dentro de cada tarjeta: prensa, saldo que se vacía,
  ciclo de recolección
- **05** — la prensa comprime el inventario y las hojas se apilan y se sellan
- **06** — el saldo baja; el estudio previo se sella *antes* de que la merma cruce
- **07** — el contenedor se llena, la unidad lo recoge, la app registra la evidencia
- **09** — las hojas se apilan en expediente y se sella
- **10** — anillos de alcance y nodos que se encienden en toda la República

**Huecos listos para fotografía real.** La clase `.foto` sustituye cualquier ilustración sin
tocar el layout: va en la columna `.viz` en lugar del `.stage`.

```html
<div class="viz r d6"><div class="foto"><img src="data:image/jpeg;base64,..." alt=""></div></div>
```

Para embeber: `base64 -i foto.jpg`. Prioridad: operación en planta (trituradora, prensa),
recolección (unidades, andén), el expediente físico, la app.

## Editar

Contenido en el `<body>`, una `<section class="s">` por lámina. Para recolorear, cambia los
tokens de `:root` — no las reglas.

Ver cambios en local: `python3 -m http.server 8000` en esta carpeta.
Publicar: `git push` — el link no cambia.

Si cambias tipografías hay que volver a empotrarlas:

```
python3 ~/.claude/skills/presentacion-web/scripts/embed_fonts.py --html index.html \
  --css-url "<URL del nuevo <link> de Google Fonts>"
```

## Carpeta

- `index.html` — el deck (~216 KB, autocontenido)
- `marca/` — variantes de logo derivadas del manual de marca 2026
  (`horizontal-claro`, `horizontal-blanco`, `isotipo-verde`, `isotipo-blanco`, `favicon-64`)

Paleta: verde `#2DA761`, oscuro `#171A1F`, claro `#F5F7FA`. Barlow (títulos) + Inter (cuerpo).

## Responsividad

Verificada en matriz. Todas estas medidas pasan sin desborde en las 12 láminas:

| Viewport | Caso |
|---|---|
| 2560x1080 / 1920x1080 | monitor grande |
| 1920x720 / 1366x660 / 1280x720 | laptop y ventana de pantalla compartida |
| 1440x810 | **referencia de diseño** |
| 1024x768 / 1024x600 / 768x1024 | tableta |
| 844x390 / 812x375 | **teléfono en horizontal** |
| 390x844 / 375x667 / 360x640 | teléfono en vertical |

Tres decisiones que la sostienen:

1. **El tamaño respeta la altura, no solo el ancho.** Los títulos y el espaciado usan
   `min(Xvw, Yvh)`: a 1440x810 el resultado es idéntico al diseño original, y en pantallas
   bajas encoge en lugar de desbordar.
2. **El apilado a una columna es solo en retrato** (`max-width:900px and orientation:portrait`).
   Un teléfono en horizontal es angosto pero bajo: apilarlo era justo lo contrario de lo que
   necesita, así que conserva las dos columnas y solo se compacta.
3. **Dos escalones de compactación por altura**: `max-height:560px` y `max-height:420px`
   aprietan padding, gaps y altura de ilustración. En láminas bajas se oculta la pista de
   navegación y el pie de ilustración.

Si agregas contenido, vuelve a correr la matriz antes de publicar — las láminas 03 (cuatro
avales + cuatro cifras) y 06 (textos de tarjeta más largos) son las que desbordan primero.

## Escala de texto chico

Todo el texto pequeño del deck usa **dos escalones únicos**. Si agregas contenido, reúsalos
en lugar de inventar un tamaño nuevo — así no vuelve a pasar que dos láminas muestren el
mismo tipo de texto en tamaños distintos:

| Escalón | Regla | @1440 | Para qué |
|---|---|---|---|
| Etiqueta | `clamp(11px,.9vw,13.5px)` | 13.0 px | eyebrows, pies de ilustración, "volver", números de tarjeta |
| Cuerpo | `clamp(12px,1.02vw,16px)` | 14.7 px | descripciones de tarjeta, listas, etiquetas de dato |

El mínimo absoluto del deck es **13.0 px**. Las etiquetas dentro de los SVG están en unidades
de viewBox y se renderizan entre 14 y 15 px reales.
