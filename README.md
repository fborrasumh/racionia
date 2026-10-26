# RacionIA

Laboratorio de nutrición animal: análisis bromatológico, balance, formulación y pastos. Aplicación web de un solo fichero.

**Usar la app:** https://fborrasumh.github.io/racionia/

**Idiomas:** español (por defecto), inglés, portugués; selector en la barra superior (o `?lang=en` / `?lang=pt` en la URL).

## Qué hace

Laboratorio de nutrición animal en el navegador que sigue el sílabo de Nutrición Animal de la Carrera de Agropecuaria (Universidad Politécnica Estatal del Carchi). El código calcula, corrige y diagnostica los errores típicos; la IA, opcional, solo hace de tutor socrático y da feedback sin notas.

- **Laboratorio de bromatología (Weende).** Datos de estufa, mufla, Kjeldahl, Soxhlet y digestión distintos para cada estudiante. Se calculan MS, ceniza, PC, EE, FC, ELN, PC tal cual y energía bruta. El código reconoce errores como olvidar el blanco, no restar la ceniza del residuo o confundir base seca y tal cual. El alimento analizado puede pasar a la tabla de materias primas.
- **Requerimientos y balance nutricional.** Simulador de una vaca lechera (ecuaciones NRC 2001 simplificadas): consumo de materia seca, ENL, proteína, calcio y fósforo, nutriente limitante, leche que permite la energía y coste por litro. Problemas individualizados con corrección por apartado.
- **Formulación de dietas y costes.** Cuadrado de Pearson con porción fija y formulador de mínimo coste por programación lineal (simplex en dos fases) para pollos de engorde, ponedoras, cerdos, cuyes y concentrado lechero. El código recomprueba cada restricción, calcula costes por kg, quintal y tonelada, muestra precios sombra y, si no hay solución, qué restricción la impide.
- **Pastos y forrajes.** Aforo por marco, materia seca por hectárea, días de ocupación, capacidad de carga y calculadora de ensilaje.
- **Condición corporal y riesgos metabólicos.** DCAD del preparto, pérdida de condición corporal y relación grasa:proteína de la leche.
- **Seis casos de aprendizaje basado en problemas:** cetosis, fiebre de leche, acidosis ruminal, tetania de los pastos, escorbuto en cuyes y enfermedad del músculo blanco. Pistas graduadas, diagnóstico corregido por código, plan de alimentación con feedback de la IA y tutor que no conoce el diagnóstico.
- **Repaso.** Simulacro de 15 preguntas sin nota (aciertos por tema), preguntas de desarrollo con feedback y 24 tarjetas con repetición espaciada.
- **Progreso y profesorado.** Cuaderno de prácticas en Word, CSV y JSON. Con un código de clase y el código de cada estudiante, el profesorado descarga las soluciones de todos los problemas o imprime los enunciados, sin servidor.

## Cómo se usa la IA

Con la propia clave de OpenAI, Google Gemini o Anthropic Claude. La clave se guarda solo en el navegador. No hace falta servidor.

## Privacidad

Todo (respuestas, fórmulas, casos, progreso y clave) se guarda solo en el navegador. A la IA solo sale lo que la persona pide revisar: el enunciado y lo que escribe, con correos, teléfonos y su código de estudiante enmascarados, tras un aviso previo con muestra. Nunca se envían las soluciones de los problemas ni el diagnóstico de los casos. El código elimina de las respuestas de la IA las frases que revelan un resultado, un diagnóstico o una nota, y marca las citas que no aparecen en el texto del estudiante.

## Límites

- La composición de las materias primas y los requerimientos son valores orientativos simplificados para docencia (NRC, FEDNA, Feedipedia). No sustituyen el análisis de laboratorio ni las tablas oficiales actualizadas, ni el asesoramiento veterinario.
- Las ecuaciones del balance son las del NRC (2001) simplificadas; no incluyen gestación, crecimiento ni actividad.
- Los problemas usan siempre la tabla de serie para que sean iguales para toda la clase.
- El filtro del tutor es una lista de términos y una comparación numérica: puede dejar pasar una formulación inesperada.
- Probado con IA simulada de los tres proveedores, en español, inglés y portugués, en escritorio y móvil. El formulador se contrastó con scipy (HiGHS) en 400 problemas sin discrepancias y los generadores, en Node, con 3000 variantes. **No se ha probado con una clave de API real.**

## Autoría

Fernando Borrás Rocher (Universidad Miguel Hernández de Elche) y Luis Rodrigo Balarezo-Urresta (Universidad Politécnica Estatal del Carchi).

Sigue el sílabo de Nutrición Animal (0811BNA6UP-AJ2025, nivel 6, Carrera de Agropecuaria, PAO 2026 B) de la Universidad Politécnica Estatal del Carchi, cuyo profesor responsable es Luis Rodrigo Balarezo-Urresta.

ORCID: Fernando Borrás Rocher [0000-0002-5519-4573](https://orcid.org/0000-0002-5519-4573) · Luis Rodrigo Balarezo-Urresta [0000-0001-5546-1259](https://orcid.org/0000-0001-5546-1259)

## Cómo citar

Borrás Rocher, F. y Balarezo-Urresta, L. (2026). *RacionIA* (v1.0.0) [Software]. (DOI en trámite)

## Licencia

MIT. Véase [LICENSE](LICENSE).
