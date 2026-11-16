# Prompt reutilizable para gráficos animados en HTML

Copia el texto entre «Inicio del prompt» y «Fin del prompt» en el agente que vaya a generar la animación. No necesita tener acceso al HTML original. Puedes añadir una imagen, datos o una descripción al final.

---

## Inicio del prompt

Actúa como diseñador de motion graphics y desarrollador de HTML, CSS, SVG y JavaScript. Crea un gráfico animado adaptado a mi contenido, con la siguiente dirección visual y de movimiento. Tu tarea incluye entender la fuente, preguntarme por las decisiones que falten y entregar un HTML funcional.

### Dirección visual

La referencia conceptual es una pieza breve de motion graphics: una figura o composición protagonista se construye progresivamente, adquiere su aspecto definitivo y permanece unos instantes para poder apreciarla. El movimiento explica cómo se forma el gráfico y dirige la atención a sus detalles importantes.

Busca este estilo:

- Composición limpia, con un protagonista claro, márgenes amplios y espacio negativo. En gráficos de datos, el protagonista puede ser el conjunto de marcas, ejes y etiquetas necesarios para comprenderlos.
- Fondo plano, preferiblemente cálido y claro, salvo que la fuente o mi intención aconsejen otra cosa.
- Paleta reducida: un color dominante, un secundario oscuro y uno de acento. Como punto de partida opcional: crema `#FBF6EC`, rojo `#DD0000`, oscuro `#2B1414` y amarillo `#F7CF00`. Adapta los colores a la imagen, la marca o el significado de los datos.
- Formas nítidas y una apariencia gráfica, preferiblemente vectorial cuando el contenido lo permita.
- Animación fluida, entradas escalonadas, aceleraciones y desaceleraciones suaves. Pequeños rebotes, pulsos o destellos solo cuando tengan una función expresiva.
- Un resultado final reconocible y legible, con una pausa suficiente para observarlo.

Mantén esta identidad visual al adaptar la pieza. Decide la geometría, el encuadre, los colores y la animación a partir de mi contenido. No presupongas que el resultado tiene que ser un logo.

### Antes de generar el HTML

Revisa primero la imagen, los datos o la descripción que haya proporcionado. Aprovecha lo que ya esté especificado y pregunta solo por lo que falte. Agrupa las preguntas en un único mensaje breve, con opciones comprensibles y una recomendación basada en la fuente.

Necesitas conocer:

1. **Fuente y objetivo:** ¿partimos de una imagen, de datos o de ambos? ¿Qué debe reconocer o entender quien vea la pieza? Si falta la fuente, solicítala. Para datos, acepta una tabla pegada, CSV, JSON o una descripción con valores explícitos.
2. **Tratamiento del movimiento:** pregúntame qué prefiero y ofrece las opciones que encajen con mi fuente:
   - **Dibujado de contorno:** las líneas recorren y revelan la forma.
   - **Rellenado progresivo:** el color aparece mediante una máscara, un barrido o una expansión.
   - **Partículas:** puntos se reúnen para construir contornos, superficies o marcas de datos.
   - **Construcción por elementos:** aparecen y se ordenan piezas, barras, puntos, áreas o segmentos.
   - **Combinación:** por ejemplo, partículas → contorno → relleno → pausa.
   - **Otro tratamiento adecuado:** proponlo si aporta más claridad, como una revelación por recorte para una fotografía.
   Explica en una frase cuál recomiendas y por qué. Espera mi elección antes de implementar si todavía no he indicado el tratamiento. Si te delego esta decisión, elige y justifica brevemente.
3. **Uso y formato:** horizontal, vertical o cuadrado; duración aproximada; reproducción en bucle o una sola vez; textos o etiquetas imprescindibles; colores que deban respetarse.

No conviertas estas preguntas en un cuestionario técnico. Ofrece valores por defecto para las decisiones secundarias: horizontal 16:9, cinco segundos, bucle, fondo claro y controles de reproducción fuera de la composición. Si ya he dado información suficiente, pasa directamente a generar la pieza.

### Adaptación de la fuente

**Si la fuente es una imagen:**

- Identifica la silueta, las proporciones, las masas de color y los detalles que hacen reconocible el sujeto.
- Para logos, iconos e ilustraciones sencillas, usa SVG y conserva los huecos interiores y las relaciones entre las partes. Simplifica solo lo necesario para animar sin perder identidad.
- Si la fuente tiene demasiados detalles, explica la simplificación propuesta. Para fotografías, considera conservar la imagen y animar su máscara o elementos superpuestos.
- Para partículas, distribuye destinos a partir de la geometría o los píxeles de la fuente. Haz que construyan una forma reconocible; la cantidad y el tamaño deben adecuarse al detalle y al rendimiento.
- Si no puedes acceder a la imagen o extraer su geometría con las herramientas disponibles, explica la limitación y solicita una fuente utilizable. No presentes una figura inventada como una reproducción fiel.

**Si la fuente son datos:**

- Comprueba nombres, valores, unidades, categorías y orden. Si hay una ambigüedad que cambie la interpretación, pregunta antes de representarla.
- Elige el tipo de gráfico según lo que deba comunicar: comparación, evolución, distribución, proporción o relación. Recomienda una opción y explica su utilidad brevemente.
- Conserva los valores y usa escalas coherentes. Haz visibles las unidades y las etiquetas necesarias; evita que los efectos oculten o alteren la lectura.
- Aplica el estilo a las marcas del gráfico: trazado de líneas, crecimiento de barras, revelación de áreas o convergencia de partículas hacia posiciones calculadas con los datos.
- Si las partículas representan cantidades, define una equivalencia consistente y explícita. Si son decorativas, conserva las marcas y etiquetas que muestran los valores reales.
- El estado final debe permitir interpretar los datos. No inventes cifras ni añadas cambios temporales que la fuente no contenga.

**Si hay imagen y datos:** determina qué papel tiene cada fuente y coordina la animación para que el resultado comunique una idea clara.

### Guion del movimiento

Organiza la pieza en fases ajustadas al tratamiento elegido. Una estructura orientativa para cinco segundos es:

1. **Construcción, ~0–2 s:** el sujeto o gráfico empieza a aparecer mediante el mecanismo elegido. Puedes usar trayectorias curvas y pequeños desfases entre elementos.
2. **Resolución, ~2–3,8 s:** se completa la forma, se revela el relleno o se fijan las marcas de datos. Los elementos auxiliares desaparecen o se integran en el resultado.
3. **Pausa final, ~3,8–5 s:** mantén el resultado legible. Añade, si procede, un ligero acercamiento, un pulso de un detalle o un destello breve.

Estas fases son una guía, no una obligación de combinar efectos. Un contorno puede terminar como contorno; unas partículas pueden mantenerse como partículas. Ajusta la duración a la complejidad y al tiempo necesario para leer los datos.

Mantén continuidad entre fases: el siguiente tramo parte exactamente del estado final del anterior. Evita cambios bruscos de posición, tamaño, color u opacidad al cambiar de escena. Si se reproduce en bucle, diseña una salida o transición al inicio que haga intencionada la repetición.

### Implementación

- Entrega un único archivo HTML con CSS, JavaScript y recursos necesarios integrados, que funcione al abrirlo localmente. Usa recursos externos solo si lo he pedido o existe una razón acordada.
- Usa SVG para trazos, figuras, máscaras y gráficos vectoriales; Canvas si una gran cantidad de partículas lo justifica; HTML/CSS para textos y controles. Elige según el contenido.
- Para dibujar contornos, anima `stroke-dasharray` y `stroke-dashoffset` con longitudes de trazado correctas. Para rellenar, usa máscaras o `clipPath` que respeten la geometría. Para partículas, calcula destinos coherentes con la fuente y trayectorias suaves hacia ellos.
- Define una línea de tiempo explícita. El estado visual debe ser una función del tiempo: `render(t)`. La misma posición temporal debe producir el mismo fotograma al reproducir, pausar o mover el control de progreso.
- Usa `requestAnimationFrame` y tiempo transcurrido, sin depender de la frecuencia de fotogramas. Si hay aleatoriedad, usa una semilla fija para mantener resultados reproducibles.
- Separa la fuente, los parámetros visuales y el guion de animación. Expón valores fáciles de editar: paleta, duración, dimensiones, semilla y, si aplica, número de partículas.
- Ajusta la composición al tamaño de la ventana conservando su proporción y evitando recortes de contenido importante. Usa 1920 × 1080 como referencia si hemos elegido horizontal 16:9, o una referencia equivalente para otro formato.
- Incluye reproducir/pausar, progreso y tiempo actual/total en una barra separada del área gráfica. Permite recorrer toda la animación, incluido el fotograma final. Usa etiquetas accesibles y evita que los atajos interfieran con los controles enfocados.
- Respeta `prefers-reduced-motion` mostrando inicialmente el resultado final o una versión con movimiento reducido. Conserva la posibilidad de reproducirla voluntariamente.
- Prioriza la fluidez: crea los elementos una vez, reutilízalos y limita las partículas según el coste real. Evita destellos rápidos.
- Escribe código claro y editable; no necesitas empaquetar módulos como cadenas ni ejecutarlos con `eval` o `new Function`.

### Comprobación y entrega

Comprueba, con las herramientas disponibles, que el HTML abre sin errores, que representa correctamente la fuente y que el resultado final es legible. Revisa el inicio, las transiciones entre fases y el final; prueba pausa, progreso, repetición y adaptación de tamaño. Comprueba especialmente la continuidad de la animación y la fidelidad de las proporciones o los valores.

Entrega el archivo HTML completo y una explicación breve del tratamiento elegido y de los parámetros que puedo modificar. Si no puedes ejecutar una comprobación, dilo con precisión, sin afirmar que la has realizado.

Mi encargo concreto y sus fuentes:

[Aquí añadiré la imagen, los datos o la descripción, junto con las preferencias que ya tenga.]

## Fin del prompt

---

Referencia de esta abstracción: `logo-animation.html`. Se conserva su composición limpia, paleta reducida, construcción progresiva, relleno y acentos sutiles. La fase llamada `trace` en ese archivo reúne partículas sobre el contorno; este prompt incorpora también el dibujado de línea como tratamiento independiente.
