---
name: html-motion-graphics
description: "Crea gráficos animados en HTML a partir de imágenes, datos o ambos, con construcción progresiva por contornos, rellenos, partículas o elementos. Úsala para piezas de motion graphics e infografías animadas con este estilo, no para animaciones generales de interfaces o sitios web."
---

# Gráficos animados en HTML

Crea una pieza de motion graphics adaptada a la fuente del usuario y entrega un HTML funcional. La identidad de esta skill es una composición limpia que se construye progresivamente, resuelve su forma y permanece legible unos instantes. Es autónoma: no requiere el HTML que inspiró su estilo.

## Acordar la pieza

Inspecciona la fuente y las preferencias ya disponibles. Si falta la imagen o los valores, solicítalos; acepta datos pegados, CSV o JSON. Antes de implementar, pregunta por el tratamiento visual si aún no está elegido. Ofrece solo las opciones pertinentes y recomienda una con una razón breve:

- Contorno: una línea recorre la geometría.
- Relleno: una máscara, barrido o expansión revela el color.
- Partículas: puntos convergen hacia contornos, superficies o marcas de datos.
- Elementos: piezas, barras, puntos o segmentos se construyen en secuencia.
- Combinación u otra revelación que encaje mejor con la fuente.

Espera la elección para implementar, salvo que el usuario haya delegado esa decisión. No vuelvas a preguntar por decisiones ya tomadas. Agrupa las dudas restantes sobre objetivo, formato, duración, bucle, colores y etiquetas en un mensaje breve. Ofrece como valores por defecto 16:9, cinco segundos, bucle y fondo claro; son configurables, no requisitos.

Para imágenes, lee [references/imagenes.md](references/imagenes.md). Para datos, lee [references/datos.md](references/datos.md). Lee ambas cuando la pieza combine fuentes.

## Dirección visual y movimiento

- Usa un protagonista claro, márgenes amplios, espacio negativo y formas nítidas. Incluye los ejes y etiquetas que requiera la lectura de datos.
- Prefiere fondo plano cálido y paleta reducida. La paleta orientativa es crema `#FBF6EC`, dominante rojo `#DD0000`, oscuro `#2B1414` y acento amarillo `#F7CF00`. Adáptala a la fuente, marca y preferencias del usuario.
- Construye → resuelve → mantén. Para cinco segundos, una distribución orientativa es 2 s, 1,8 s y 1,2 s. Ajusta el tiempo a la complejidad y la lectura.
- Usa entradas escalonadas y aceleración/desaceleración suave. Reserva rebotes pequeños, pulsos o destellos para detalles que merezcan atención.
- El tratamiento elegido determina las fases: un contorno puede permanecer como contorno y unas partículas como partículas; no impongas un relleno final.
- Conserva exactamente el estado visual entre fases. Diseña el regreso al inicio si hay bucle, evitando un salto accidental.

## Construir el HTML

Entrega un archivo autónomo con estilos, JavaScript y recursos integrados, que abra localmente. Usa recursos externos cuando el usuario los pida o acuerde. En proyectos existentes, respeta su organización y las librerías elegidas.

Elige SVG para geometría, trazado, máscaras y marcas vectoriales; Canvas cuando la cantidad de partículas justifique su coste; HTML/CSS para textos y controles. Para contornos, calcula longitudes y anima `stroke-dasharray`/`stroke-dashoffset`; para relleno usa máscaras o `clipPath`; para partículas deriva destinos de la fuente.

Implementa una línea de tiempo con `render(t)`: el mismo tiempo produce el mismo fotograma, también al retroceder con el control de progreso. Usa `requestAnimationFrame`, tiempo transcurrido y aleatoriedad con semilla fija si procede. No bases el resultado en acumulación por fotograma ni en animaciones que no puedan sincronizarse con el progreso.

Separa fuente, configuración y animación. Expón paleta, duración, dimensiones, semilla y cantidad de partículas si aplica. Crea y reutiliza los elementos; ajusta el coste al contenido. Escribe funciones o módulos directamente, sin empaquetarlos como cadenas ejecutables.

Escala la composición conservando su proporción, sin recortar información importante. Para 16:9 usa como referencia 1920 × 1080; adapta otros formatos.

Incluye reproducir/pausar, progreso y tiempo actual/total fuera del área gráfica salvo otra preferencia del usuario. Permite seleccionar el fotograma final. Usa controles accesibles; los atajos no deben interferir con controles enfocados. Con `prefers-reduced-motion`, muestra inicialmente el resultado final o una versión reducida y permite reproducir voluntariamente.

## Verificar y entregar

Con las herramientas disponibles, abre el HTML y comprueba inicio, fronteras entre fases, final y repetición. Prueba pausa, progreso hacia delante y atrás, y adaptación de tamaño. Verifica reconocimiento de la imagen o fidelidad de valores y escalas, según la fuente. Corrige errores y discontinuidades antes de entregar.

Entrega el HTML y explica brevemente el tratamiento y los parámetros editables. Indica las comprobaciones realizadas y cualquier limitación concreta; no afirmes verificaciones que no hayas ejecutado.
