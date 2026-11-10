---
name: buscar-referencias
description: Busca y verifica referencias bibliográficas para las afirmaciones de la memoria (capítulos en Chapters/). Usar cuando el usuario pida referencias, fuentes o respaldo para una afirmación, sección o capítulo, o cuando una afirmación no tenga cita. Propone referencias reales con su ubicación exacta y las agrega a references.bib solo si el usuario lo aprueba.
---

# Buscar referencias para la memoria

Objetivo: encontrar, para cada afirmación de la memoria que lo necesite, una fuente real y verificada, indicando dónde exactamente se sostiene lo afirmado, para que el autor pueda comprobarlo.

Argumento opcional: capítulo, sección, párrafo o frase concreta (por ejemplo `1.2` o "la frase sobre complejidad computacional"). Sin argumento, preguntar qué parte revisar.

## Reglas inamovibles (de CLAUDE.md)

- No afirmar nada sin una fuente verificada. Prohibido inventar referencias, DOIs, páginas, figuras o cifras.
- No citar de memoria secciones, figuras ni cifras de un paper sin haberlo leído en esta sesión.
- Si no se pudo leer la fuente (paywall, sin acceso, solo abstract), decirlo explícitamente y marcarla como "no verificada". No darla por buena.
- No mencionar ni citar el paper de ULCNN (Guo et al. 2022), ni en el texto ni en `references.bib`.
- No usar guiones largos (—) en ningún texto de la memoria ni en las propuestas de redacción.
- La sección "Estado del arte" solo describe el estado previo al trabajo, con referencias. No relacionarla con el trabajo realizado.
- Las imágenes se referencian con notas al pie, no con `[N]`.
- Redacción impersonal y en pasado; sin negritas ni subrayado; `\texttt{}` solo para nombres literales de la implementación (no para tecnologías, modelos, métricas ni datasets externos).

## Procedimiento

1. **Leer el contexto**
   - Leer el capítulo/sección pedido en `Chapters/`.
   - Leer `referencias_cap1.md`, `references.bib` y la sección "Estado de referencias" de `CLAUDE.md` para no duplicar ni contradecir lo ya mapeado o ya verificado.
   - Si la afirmación depende de resultados del trabajo (no de literatura), leer `D:\CEIA\Proyecto_AMC\CLAUDE.md`: esos datos se respaldan con el propio trabajo, no con una cita externa.

2. **Extraer afirmaciones**
   Listar las afirmaciones que requieren respaldo: definiciones, datos cuantitativos, atribuciones ("se ha demostrado que"), comparaciones entre métodos, descripciones de datasets o herramientas externas. Descartar las que son resultados propios o de sentido común. Mostrar la lista numerada al usuario antes de buscar si son más de unas pocas.

3. **Reutilizar antes de buscar**
   Si una entrada de `references.bib` ya cubre la afirmación y figura como verificada, proponer reutilizar su clave. Las marcadas "sin verificar" (`swami2000hierarchical`, `rajendran2018deep`) no se usan hasta verificarlas.

4. **Buscar**
   - Usar WebSearch (modo estándar; extendido solo si el resultado es pobre) y preferir: libros de referencia, artículos en revistas y congresos con revisión por pares (IEEE, ACM, Elsevier, Springer), arXiv solo si es la fuente original del dataset o método.
   - Priorizar la fuente primaria de una afirmación (quien introdujo el método o el dataset) sobre reseñas que la repiten.
   - Evitar blogs, resúmenes de terceros y páginas sin autoría.

5. **Verificar leyendo**
   - Abrir la fuente (WebFetch o el agente `web-fetch`; para PDFs, descargar a una carpeta propia del scratchpad y leer con Read/pdf, con permiso del usuario según corresponda).
   - Localizar el pasaje exacto que respalda la afirmación: sección, página, figura o tabla.
   - Comprobar que la fuente dice lo que la afirmación dice, no algo más fuerte. Si respalda solo parcialmente, proponer reformular la afirmación en lugar de forzar la cita.
   - Confirmar autores, título, medio, año y DOI/ISBN desde la página del editor o Crossref, no de memoria.

6. **Reportar** (formato abajo) y esperar aprobación antes de editar archivos.

7. **Incorporar (solo con aprobación del usuario)**
   - Agregar la entrada BibTeX a `references.bib` con clave `apellidoañoPalabra` en minúsculas (como `oshea2016convolutional`), sin campos inventados.
   - Insertar `\cite{clave}` en el `.tex` en la frase correspondiente.
   - Actualizar `referencias_cap1.md` (o el archivo del capítulo correspondiente) y la sección "Estado de referencias" de `CLAUDE.md` con el estado: verificada leyendo / solo abstract / no verificada.

## Formato del reporte

Por cada afirmación:

```
Afirmación N: "<texto tal cual figura en la memoria>" (Chapter X, sección Y)
Referencia propuesta: Autores (todos o "et al." con primeros), "Título", Medio, volumen/páginas, año. DOI/ISBN.
Dónde se sostiene: sección / página / figura / tabla concreta, con una paráfrasis breve de lo que dice ahí.
Estado: LEÍDA COMPLETA | LEÍDA PARCIAL (indicar qué) | NO VERIFICADA (indicar por qué)
Calce: respalda totalmente | respalda parcialmente (sugerir reformulación) 
Clave BibTeX sugerida: apellidoañopalabra (o "ya existe: clave")
```

Si no se encuentra una fuente que respalde la afirmación, decirlo claramente y ofrecer: reformularla con lo que sí está respaldado, citar el propio trabajo, o eliminarla. Nunca rellenar con una cita dudosa.

## Notas

- Citas en el texto con formato `[N]`; la numeración la resuelve la plantilla a partir de la bibliografía.
- Al parafrasear una fuente en la propuesta de redacción, no reproducir textualmente más de lo mínimo (una cita corta entre comillas como máximo).
- Evitar frases típicas de ChatGPT ("en resumen", "en conclusión", "en conjunto", "en síntesis").
