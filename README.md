# humanizer-es

Una skill para que la IA escriba **en español** con muchos menos tics de IA.

No es un detector: no decide si un texto lo ha escrito una máquina ni demuestra lo contrario. Es una lista de patrones y calcos revisada a mano, con los falsos positivos que eso implica, más un hueco para tu voz que tienes que rellenar tú.

No es una traducción del [`humanizer`](https://github.com/blader/humanizer) original. Hereda de él los patrones universales y le añade la capa que solo tiene sentido en español.

## Por qué traducir el humanizer inglés no basta

El humanizer original cubre muy bien los patrones que son universales, como el "no es X, es Y", las tríadas forzadas o el abuso de rayas, y él mismo avisa de que esas fórmulas aparecen en cualquier idioma. Esa parte no hace falta reinventarla.

El problema aparece al traducir sus reglas tal cual. Uno de los ejemplos que más se citan en inglés es *delve into*. Tradúcelo y te queda "profundizar en", que en español es de lo más normal, así que has cazado un fantasma.

Mientras tanto se te cuelan los que sí nos suenan raro a nosotros y que una lista pensada desde el inglés no recoge igual:

- **"es importante de mencionar"**, un calco directo de *it's important to mention*. En español se dice "hay que mencionar", o directamente no se dice.
- **"al final del día"**, que sale de *at the end of the day* cuando lo que decimos es "a fin de cuentas".
- **El gerundio encadenado**, del tipo "lanzó el producto, consiguiendo un aumento de ventas". Ojo, porque es correcto en español y lleva siglos en el idioma. Lo que chirría es la frecuencia con la que lo usa un modelo, cuando una persona casi siempre escribiría "lanzó el producto y las ventas subieron".
- **Los falsos positivos propios**: reglas que traducidas acaban marcando como error frases que en español están perfectamente bien.

Por eso este repo no intenta rehacer la parte universal y se centra en la capa española.

## Qué hace, en tres pasadas

**1. Quita los patrones de IA.** Veintiuno que hacen que un texto suene a generado: la raya larga metida en medio de una frase, la construcción de "no es solo X, sino Y", las tríadas de tres elementos, los "cabe destacar", los gerundios decorativos, las atribuciones vagas de "los expertos coinciden", las negritas puestas por simetría y los cierres de "en definitiva".

**2. Corrige los calcos.** Tildes, ñ, signos de apertura, y sobre todo una tabla con veintitrés calcos léxicos y cinco estructuras calcadas del inglés, que es la parte que no vas a encontrar en ningún fichero traducido.

**3. Le pone tu voz.** Esta parte va vacía a propósito y la tienes que rellenar tú, porque una voz prestada no sirve de nada. Dentro tienes las instrucciones para hacerlo en diez minutos a partir de tres textos tuyos.

## Cómo se usa

**Con Claude Code.** Copia la carpeta en `.claude/skills/humanizer-es/` de tu proyecto y ya está. Se invoca sola cuando escribes algo, o la llamas con `/humanizer-es`.

**Con ChatGPT, Gemini o cualquier otro chat.** Usa [`humanizer-es-portable.md`](humanizer-es-portable.md), que es lo mismo en una sola pieza. Lo pegas en las instrucciones personalizadas o en un proyecto, y a correr.

Lo primero que tienes que hacer, en los dos casos, es rellenar la sección del perfil de voz.

## El paso que casi nadie da

Una skill así, tal cual, es una foto. Una foto de tu estilo el día que la rellenaste, hecha además por ti, que eres justo quien peor sabe describir cómo escribe.

Y las fotos envejecen. Cambias de tema, cambias de canal, cambias de modelo, y la foto sigue diciendo lo mismo que decía en marzo.

Lo que hace que esto funcione de verdad es [`registro-correcciones.md`](registro-correcciones.md), que es una tabla de cuatro columnas donde apuntas cada corrección que le haces: lo que te devolvió, lo que tú habrías escrito, y **por qué**.

Esa cuarta columna es la que casi nadie pone y la que más rinde. Si solo apuntas que cambiaste una palabra por otra, has arreglado esa frase. Si apuntas la razón, has arreglado las mil frases siguientes.

Aquí va vacía. La mía lleva más de cien filas y sigue creciendo cada semana.

Y para que aguante, la captura no puede depender de que te acuerdes, porque una tabla que hay que rellenar a mano dura tres semanas exactas. En **[kit-consistencia](https://github.com/alvaromieres9/kit-consistencia)** está el sistema que la mantiene: un hook que detecta cuando tu mensaje trae una frase de corrección, la skill `voz` que interpreta el cambio y escribe la fila, y un barrido al cerrar la sesión para recuperar lo que se escapó.

## Contexto

Esto salió de un problema que tenía todos los días, y lo conté entero aquí: [Llevaba meses corrigiendo las mismas tres cosas a la IA. Así conseguí que dejara de olvidarlas](https://alvarobuildsai.substack.com/p/llevaba-meses-corrigiendo-las-mismas-tres-cosas).

## Licencia

MIT. Haz lo que quieras con ello.

Si cazas un patrón en español que aquí no esté, mándamelo. Lee [CONTRIBUTING.md](CONTRIBUTING.md).
