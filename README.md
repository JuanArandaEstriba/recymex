# RECYMEX® · Presentación para llamada comercial

Deck web de **13 láminas** para la llamada de 15–20 min que sigue al primer contacto por
WhatsApp. Objetivo único: **vender uno de los tres servicios** y salir con la información
para cotizar.

Un solo archivo (`index.html`), autocontenido: Barlow + Inter empotradas en base64, logos
embebidos, **cero referencias externas**. Se abre en cualquier navegador, con o sin internet.

## Cómo se presenta

- **Escritorio:** flechas ← →, barra espaciadora, o clic en los costados.
- **Celular:** swipe.
- **Puntos abajo:** salto a cualquier lámina. Contador abajo a la derecha.
- **Ramificado:** en la lámina 04 le picas al servicio que aplica y salta directo. Cada
  lámina de servicio trae **← SERVICIOS** para volver. Si prefieres verlos los tres, sigue
  con la flecha.

Para Zoom/Meet: abre el archivo, F11 y comparte pantalla.

## Recorrido (13 láminas · 11 por llamada con ramificación)

| # | Lámina | Trabajo que hace |
|---|---|---|
| 01 | Portada | Soluciones integrales en manejo y destrucción de residuos |
| 02 | Nos llevamos el problema completo | Qué hacemos, en positivo |
| 03 | No somos un flete | Los cinco avales + capacidad |
| 04 | **¿Cuál de los tres es tu caso?** | Hub ramificado. Aquí se autoselecciona |
| 05 | Destrucción fiscal | Liberas almacén, sacas de libros, deduces |
| 06 | Residuos IMMEX | Bajas el saldo antes de que venza |
| 07 | Gestión de residuos | Arranca en días |
| 08 | Cómo trabajamos | Las tres etapas |
| 09 | El entregable es el expediente | Aquí se vende la tranquilidad |
| 10 | Cobertura y quién ejecuta | Mata dos objeciones de golpe |
| 11 | Para cotizarte | Los datos, en 4 preguntas |
| 12 | No todos tardan lo mismo | Tiempos honestos **por servicio** |
| 13 | Siguiente paso | Compromiso con fecha de los dos lados + contacto |

## Criterios de fondo

- **No se asume que todo lleva trámite ante el SAT.** El aviso de 30 días hábiles aplica a la
  destrucción fiscal *con deducción*. Gestión de residuos no lleva trámite fiscal y arranca en
  días; IMMEX va por descargo aduanal, que es otra ruta. La lámina 12 lo separa, y eso es
  argumento de venta, no letra chiquita.
- **La 04 enseña antes de vender.** Muchos prospectos no saben que existen rutas distintas.
  Ver las tres y entender que no todas llevan trámite es lo que abre la conversación.
- **La 13 pone fecha propia de RECYMEX** (acuse en 24 h, cotización en 5–15 días). En las
  15 conversaciones revisadas, las tareas del cliente traían fecha y las de RECYMEX casi nunca.
- **Sin nombres de presentador**, para que la pueda dar cualquiera del equipo.

## Ilustraciones

Seis animaciones SVG hechas a mano, cada una es el *verbo* de su lámina:
convergencia de las tres corrientes (02), prensa que comprime y sello que certifica (05),
barra de saldo que se vacía al cruzar la temporalidad (06), contenedor que se llena y unidad
que lo recoge cada semana (07), hojas que se apilan en expediente (09).

**Huecos listos para fotografía real.** La clase `.foto` sustituye cualquier ilustración sin
tocar el layout: se pone en la columna `.viz` en lugar del `.stage`.

```html
<div class="viz r d6"><div class="foto"><img src="data:image/jpeg;base64,..." alt=""></div></div>
```

Para embeber una foto: `base64 -i foto.jpg`. Prioridad de fotos: operación en planta
(trituradora, prensa), recolección (unidades, andén), el expediente físico, la plataforma.

## Pendiente

- **Nombres de clientes.** No se nombra a ninguno. Si hay permiso, la lámina 03 aguanta una
  línea de referencias y sube mucho.
- **Plataforma de seguimiento (lámina 09).** Redactada como capacidad real sin prometer
  funciones que no estén vivas. Revisar contra el estado del desarrollo.

## Editar

Contenido en el `<body>`, una `<section class="s">` por lámina. Para recolorear, cambia los
tokens de `:root` — no las reglas.

Ver cambios: `python3 -m http.server 8000` en esta carpeta.

Si cambias tipografías hay que volver a empotrarlas:

```
python3 ~/.claude/skills/presentacion-web/scripts/embed_fonts.py --html index.html \
  --css-url "<URL del nuevo <link> de Google Fonts>"
```

## Carpeta

- `index.html` — el deck (~214 KB, autocontenido)
- `marca/` — variantes de logo derivadas del manual de marca 2026
  (`horizontal-claro`, `horizontal-blanco`, `isotipo-verde`, `isotipo-blanco`, `favicon-64`)

Paleta: verde `#2DA761`, oscuro `#171A1F`, claro `#F5F7FA`. Barlow (títulos) + Inter (cuerpo).
