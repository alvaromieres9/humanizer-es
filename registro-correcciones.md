# Registro de correcciones

> **Qué es esto.** Tus correcciones reales sobre textos que la IA ya te ha devuelto "limpios". **Mandan sobre cualquier regla genérica de la skill**: si aquí dice una cosa y el manual dice otra, gana esto.
>
> **Por qué importa más que la propia skill.** El manual describe cómo se escribe bien en general. Esta tabla describe cómo escribes tú, y lo hace con pruebas en vez de con adjetivos. Está medido que darle entre tres y cinco ejemplos reales en lugar de una descripción mejora bastante la adherencia a lo que le pides.
>
> **La columna del porqué es la importante.** Si solo apuntas que cambiaste una palabra por otra, has arreglado esa frase. Si apuntas la razón, has arreglado las mil frases siguientes, incluidas las que todavía no has escrito. Es la columna que casi nadie pone.

## Reglas del registro

- **Una fila por corrección atómica.** Si en un texto cambiaste cuatro cosas, son cuatro filas.
- **El campo "Por qué" es obligatorio.** Si no lo tienes claro en el momento, escribe `(sin explicitar)`, pero nunca te lo inventes.
- **Nunca se borra una fila.** Si un criterio se afina con el tiempo, se añade otra con la fecha nueva. El historial es parte del valor.
- **Cero invención.** Solo entra lo que de verdad corregiste.
- **Se lee entero antes de escribir**, no solo al final.

## Cómo empezar sin tener nada

No necesitas cien filas para que se note. Con cinco ya cambia el resultado.

Coge los tres últimos textos que la IA te devolvió y tuviste que retocar. Mira qué le cambiaste. Esas son tus cinco primeras filas, y las tienes en diez minutos.

## Cómo hacer que se llene solo

Esta tabla, rellenada a mano, dura tres semanas. Lo sé porque lo probé.

En [kit-consistencia](https://github.com/alvaromieres9/kit-consistencia) tienes cómo montarlo. Un hook detecta cuando tu mensaje trae una frase como "esto no me gusta"; la skill `voz` coge el antes y el después, te pregunta el porqué si no lo has dicho y escribe la fila; y un barrido al cerrar la sesión recupera las que se escaparon, como cuando reescribes una frase sin decir nada.

---

| Fecha | Antes (lo que salió) | Después (lo que tú quieres) | Por qué (el racional) |
|---|---|---|---|
| AAAA-MM-DD | | | |
