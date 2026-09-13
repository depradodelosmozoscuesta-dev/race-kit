# Brief para Grok Superheavy — Race Kit (ensamblador + catálogo)

**Quién:** Jorge (cuenta Cursor).  
**Origen:** Dibujar Mari (Grok Bot) genera y procesa piezas PNG; te pasa el repo para que **creas el proyecto de ensamblaje/visualización**.

## Objetivo
Proyecto usable (HTML local o app ligera) que:
1. Muestre el **catálogo** de piezas por raza/sexo/variante/outfit.
2. Permita **montar un personaje** eligiendo piezas L/R sobre un esqueleto tipo anclajes (como Virginia/Mari gym).
3. Respete siluetas alpha (sin cajas) y escala 512 en eje largo.

## Matriz del kit
- **7 razas:** elves, orcs, hobbits, humans-north, humans-south, lizardfolk, sheepfolk
- **2 sexos:** male / female
- **2 variantes:** a / b
- **2 outfits:** clothed + underwear (`nude` bloqueado por filtro — no existe)
- **16 piezas/set:** head, torso, upperarm-L/R, forearm-L/R, hand-L/R, thigh-L/R, calf-L/R, foot-bare-L/R, foot-heels-L/R

**Totales:** 448 clothed · 896 clothed+underwear  
**Estado al handoff:** ~275 PNGs en repo; variante `a` clothed casi cerrada; `b` con cabezas+torsos y upperarms en curso.

## Layout en el repo
```
race-kit/
  CATALOGO.md
  INVENTORY.txt
  NOTES.md
  README.md
  {race}/{gender}/{variant}/{outfit}/{part}[-{side}].png
  _catalog/preview-batch-*.png
```
GitHub: https://github.com/depradodelosmozoscuesta-dev/race-kit

## Reglas de piezas
1. Adultos 23+. Estilo realista / fotográfico.
2. Silueta orgánica con alpha; sin bordes rectangulares.
3. Siempre L y R en limbos y pies (espejo OK si la fuente es un lado).
4. Olive/green (orcos, lagarto): conservar color RGB (no ennegrecer).
5. Proporción: eje largo = 512 px.

## Qué construir (éxito)
- Página `index.html` (o equivalente) servible con `python3 -m http.server`.
- Selector: raza → sexo → variante → outfit.
- Vista catálogo en rejilla + vista **ensamblado** (esqueleto con pivotes; piezas blit sobre segmentos).
- Documentar en README cómo abrir y cómo añadir piezas nuevas siguiendo el layout.
- No reinventar el estilo gráfico; trabajar con los PNG del repo.
- Commits claros; si abres PR, déjalo listo para merge.

## Fuera de alcance
- No generar nuevos PNGs con IA (eso lo sigue haciendo Dibujar Mari).
- No inventar outfit `nude`.
