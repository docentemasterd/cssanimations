# cssanimations
Animaciones con CSS3

Las animaciones CSS3 permiten animar la transición entre un estilo CSS y otro. Las animaciones constan de dos componentes: un estilo que describe la animación CSS y un conjunto de fotogramas que indican su estado inicial y final, así como posibles puntos intermedios en la misma.

Las animaciones CSS tienen tres ventajas principales sobre las técnicas tradicionales de animación basada en scripts:

-Son muy fácil usar para animaciones sencillas, puedes hacerlo incluso sin tener conocimientos de Javascript.
-La animación se muestra correctamente, incluso en equipos poco potentes. Animaciones simples realizadas en Javascript pueden verse mal (a menos que estén muy bien echas). El motor de renderizado puede usar técnicas de optimización como el "frame-skipping" u otras tecnicas para manteber que la animación se vea tan suave como sea posible.
-Al ser el navegador quien controle la secuencia de la animación, permitimos que optimice el rendimiento y eficiencia de la misma, por ejemplo, reduciendo la frecuencia de actualización de la animación ejecutándola en pestañas que no estén visibles.

*Configurando la animacion*
===========================
Para crear una secuencia de animación CSS, tu estilizarás el elemento que quieras animar con la propiedad animation y sus sub-propiedades. Con ellas podemos no solo configurar el ritmo y la duración de la animación sino otros detalles sobre la secuencia de la animación. Con ellas no configuramos la apariencia actual de la animación, para ello disponemos de @keyframes como describiremos más adelante .

Las subpropiedades de animation son:

animation-delay:
Tiempo de retardo entre el momento en que el elemento se carga y el comienzo de la secuencia de la animación.

animation-direction:
Indica si la animación debe retroceder hasta el fotograma de inicio al finalizar la secuencia o si debe comenzar desde el principio al llegar al final.

animation-duration:
Indica la cantidad de tiempo que la animación consume en completar su ciclo (duración).

animation-iteration-count:
El número de veces que se repite. Podemos indicar infinite para repetir la animación indefinidamente.

animation-name:
Especifica el nombre de la regla @keyframes que describe los fotogramas de la animación.

animation-play-state:
Permite pausar y reanudar la secuencia de la animación

animation-timing-function:
Indica el ritmo de la animación, es decir, como se muestran los fotogramas de la animación, estableciendo curvas de aceleración.

animation-fill-mode:
Especifica qué valores tendrán las propiedades después de finalizar la animación (los de antes de ejecutarla, los del último fotograma de la animación o ambos).

*Definiendo la secuencia de la animación con fotogramas*
========================================================
Una vez configurado el tiempo de la animación, necesitamos definir su apariencia. Esto lo haremos estableciendo dos fotogramas más usando la regla @keyframes. Cada fotograma describe cómo se muestra cada elemento animado en un momento dado durante la secuencia de la animación.

Desde que se define el tiempo y el ritmo de la animación, el fotograma usa percentage para indicar en qué momento de la secuencia de la animación tiene lugar. 0% es el principio, 100% es el estado final de la animación. Debemos especificar estos dos momentos para que el navegador sepa dónde debe comenzar y finalizar; debido a su importancias, estos dos momentos tienen alias especiales: from y to.

Además puedes, opcionalmente, incluir fotogramas que describan pasos intermedios entre el punto inicial y final de la animación.

CSS ofrece la posibilidad de resumir todas estas propiedades en una sola, para hacer nuestras hojas de estilos más específicas. El orden de la propiedad de atajo sería el siguiente:

div {
    animation: <name> <duration> <timing-function> <delay> <iteration-count> <direction> <fill-mode> <play-state>
}

Consejo: Mucho cuidado al indicar los segundos en las propiedades de duración. Al ser una unidad diferente a las que solemos manejar (px, em, etc...) hay que especificar siempre la s, aunque sea un valor igual a 0.
  
  
 * Fuente: Developer Mozilla > Animaciones CSS
