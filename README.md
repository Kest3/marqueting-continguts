# Marqueting de Continguts — generador estático propio + CMS en catalán

**Caso de estudio.** Este repositorio documenta el proyecto. El código no es público: es un encargo de un cliente.

---

## El problema

Migrar un WordPress a algo que pudiera mantener una persona no técnica, sin llamar a nadie y sin que se rompiera solo con el tiempo.

## La decisión de diseño

Lo obvio era usar un generador estático conocido: Astro, Eleventy, Hugo. Todos traen un árbol de dependencias que hay que ir actualizando y que, en un proyecto que nadie va a tocar en dos años, acaba siendo deuda.

Elegí lo contrario: **escribir el generador, sin ninguna dependencia**.

- `build.js` — **226 líneas**. Lee el contenido, aplica las plantillas y escribe el HTML.
- `templates.js` — **950 líneas**. Las plantillas, en JavaScript plano.
- Node y nada más. Cero paquetes de terceros: no hay `npm audit` que atender, ni versión mayor que migrar, ni superficie de ataque heredada.

El resultado es HTML estático puro: rápido, indexable y sin nada corriendo en el servidor.

## El panel de edición

**Decap CMS** con Git Gateway, en catalán:

- la administradora entra con su correo, sin usuario de servidor ni acceso al hosting;
- los formularios son mínimos —título, texto, imagen— sin un solo campo técnico a la vista;
- cada cambio queda como un commit en Git, así que hay historial completo y cualquier cosa se puede deshacer;
- Netlify reconstruye y publica sola.

Es la parte de la que estoy más contento: la administradora publica sin saber que por debajo está haciendo commits.

## Qué se entregó además

- Manual de la administradora, escrito para ella y no para un técnico.
- Informe de migración: qué se trajo del WordPress y cómo.
- Justificación escrita del stack, para que quien venga detrás entienda por qué no hay un framework.

## Autor

Kevin Stiven Guzmán Ovalle — Escaldes-Engordany, Andorra.

[LinkedIn](https://linkedin.com/in/kevin-guzman-ovalle) · kevin22guzman@gmail.com
