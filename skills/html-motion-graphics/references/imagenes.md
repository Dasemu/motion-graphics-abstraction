# Adaptación de imágenes

Identifica silueta, proporciones, masas de color y detalles que permiten reconocer el sujeto. Conserva las relaciones entre partes y los huecos interiores. Para logos, iconos e ilustraciones sencillas, SVG permite animar la geometría con nitidez.

Simplifica según el tamaño de salida y el tratamiento elegido. Si la simplificación cambia detalles relevantes, explica la propuesta antes de implementarla. No sustituyas una fuente inaccesible por una figura inventada presentada como reproducción: solicita una imagen utilizable o una alternativa acordada.

En fotografías o imágenes complejas, considera conservar el recurso y animar una máscara o superponer elementos. El trazado vectorial no es obligatorio si reduce la fidelidad. Integra la imagen en el HTML cuando deba ser autónomo.

## Elegir destinos de partículas

- Para contornos, muestrea posiciones por longitud de trazado para repartir puntos de forma regular.
- Para superficies, muestrea dentro de la figura o sobre píxeles visibles, respetando transparencia y huecos.
- Conserva colores por región cuando ayuden al reconocimiento.
- Ajusta densidad y radio al detalle; comprueba que el estado final conserva la identidad.
- Puedes usar trayectorias curvas, desfases y pequeñas oscilaciones que se atenúen al llegar. Al pasar a relleno sólido, retira las partículas de forma coordinada con la máscara, sin duplicar o desplazar la figura.

## Contorno y relleno

En trazados con varias partes, decide si se dibujan secuencialmente o en paralelo según su jerarquía. Conserva la regla de relleno apropiada y la geometría de huecos. El origen y la dirección del relleno deben apoyar la composición; una expansión radial es una opción, no un rasgo obligatorio.
