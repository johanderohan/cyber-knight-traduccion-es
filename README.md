# Cyber Knight — Traducción al español

[![Invítame a un café en Ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/johanderohan)

Ficha del proyecto, capturas y más traducciones al castellano en **[Parches en Castellano](https://parchesencastellano.com/traducciones/pc-engine/cyber-knight)**.

Traducción al **español de España** de *Cyber Knight* (サイバーナイト, PC Engine,
1990), el RPG de ciencia ficción de Tonkin House con guion de Group SNE, que nunca
salió de Japón. La tripulación de la nave SS Swordfish, perdida tras un salto
fallido en el centro de la galaxia, busca el camino de vuelta a la Tierra mientras
se enfrenta a los berserkers.

La traducción se ha hecho **directamente desde el japonés** de la HuCard original y
se reparte como **parche**: no incluye el juego. Necesitas tu propia copia para
aplicarlo.

## Estado

Última versión: **[v1.0](../../releases/tag/v1.0)**.

| Parte | Estado |
|---|---|
| Guion | **1.114 de 1.114 mensajes con texto** traducidos (todo el guion del motor de texto) |
| Menús, combate, objetos, enemigos y armas | Traducidos, incluidas las palabras que el original dibuja en kanji |
| Pantalla de nombre | Página de letras españolas; el nombre admite 4 letras, como el original |
| Caracteres españoles | **á é í ó ú ü ñ Á É Í Ó Ú Ü Ñ ¡ ¿ « » — …** |
| Logotipo, cartelas y créditos | Se conservan los originales |
| Revisión durante una partida completa | Pendiente |

### Qué incluye el parche

- Fuente con los caracteres españoles, dibujada con el mismo trazo y el mismo
  blanco sobre azul que la original. Además, las minúsculas **p, q, g, y** se han
  redibujado: en la fuente japonesa parecían mayúsculas.
- Nueva maquetación: las líneas se ajustan al ancho real de cada ventana y los
  textos largos pasan de página con la misma pausa que usa cada escena.
- Menús de la nave y de combate más anchos para que las órdenes se lean enteras
  («Despegar», «Accesorio», «Luchar»…).
- Como el castellano ocupa más que el japonés y la HuCard estaba llena, la imagen
  pasa de 4 a **8 Mbit** y el guion se reparte en bancos nuevos. El motor de texto
  se ha ajustado para que cada mensaje se lea siempre de su propio banco.

### Comprobaciones y trabajo pendiente

- Cada mensaje se ha validado con un comprobador que conoce el ancho de cada
  ventana, las pausas y los controles del motor.
- Los mensajes con ventana propia se han mostrado uno a uno en el emulador y su
  texto se ha leído en pantalla tesela a tesela, para comprobar que ninguna línea
  queda cortada.
- Se han jugado el inicio, la introducción, el puente, las salas de la nave, la
  salida al primer planeta y un combate.
- El parche se ha aplicado sobre la HuCard japonesa original y el resultado se ha
  comparado byte a byte con la imagen probada.

**Queda pendiente una partida completa** de principio a fin y la prueba en consola
real. La traducción y su revisión se han hecho con asistencia de modelos de
lenguaje; no ha habido todavía una revisión humana independiente. Si encuentras un
error, abre una incidencia con una captura.

## Cómo aplicar el parche

1. Descarga el parche `.xdelta` de la sección **[Releases](../../releases)**.
2. Consigue tu copia de la HuCard **japonesa** original. El parche solo funciona
   con esa versión exacta, **sin cabecera** de 512 bytes.
3. **Comprueba que tu copia es la correcta** antes de nada:

   | | |
   |---|---|
   | Archivo | `Cyber Knight (Japan).pce` |
   | Tamaño | 524.288 bytes (4 Mbit) |
   | CRC32 | `A594FAC0` |
   | MD5 | `dad257d4984635f70580b10f1ae1b75c` |

   ```bash
   md5sum "Cyber Knight (Japan).pce"     # Linux
   md5 "Cyber Knight (Japan).pce"        # macOS
   CertUtil -hashfile "Cyber Knight (Japan).pce" MD5   # Windows
   ```

   Si no coincide, el parche fallará o dará un resultado corrupto.
4. Aplica el parche con una de estas herramientas:
   - **Windows**: [Delta Patcher](https://github.com/marco-calautti/DeltaPatcher/releases)
   - **Linux / macOS**: `xdelta3 -d -s "Cyber Knight (Japan).pce" cyber-knight-es-v1.0.xdelta "Cyber Knight (ES).pce"`
5. Comprueba que la imagen resultante mide **1.048.576 bytes** y tiene MD5
   **`b163cbaf2a04ce68730b4150979d9834`**.
6. Cárgala en un emulador o flashcart que admita HuCards de 8 Mbit.

Aplica cada versión sobre la **HuCard japonesa original**, no sobre una imagen ya
traducida.

## Aviso

Este proyecto es una traducción hecha por afición, sin ánimo de lucro y sin
relación alguna con Tonkin House ni con Group SNE. Aquí no se distribuye el juego
ni ninguna parte de él: solo un parche que modifica una copia que ya tengas.

Si eres el titular de los derechos y quieres que retire esto, abre una incidencia
y lo hago.
