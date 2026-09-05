# Mantenimiento, actualización y control de calidad de esta base

Ver [[00-resumen-ejecutivo]]. Esta ficha no responde dudas de FUNDAE: dice **cómo se cuida la
base** para que las respuestas sigan siendo ciertas dentro de un año.

## Por qué no vale tratarla como un documento anual

El ejercicio 2026 es la demostración: conviven la Ley 30/2015, el RD 694/2017 consolidado, una
modificación publicada el 31-dic-2025 con efectos desde el 1-ene-2026 y una resolución
específica solo para las acciones de 2026. Una FAQ correcta en 2024 o 2025 puede estar
**incompleta** en 2026, sobre todo en plazos, aula virtual y procedimiento de comprobación.

## Jerarquía obligatoria de fuentes

1. **BOE y textos consolidados.** Es lo único que cierra una respuesta con impacto económico.
2. **SEPE, FUNDAE y TGSS** para la operativa (aplicación, guías, orientaciones de costes, RED).
3. **Ministerios y servicios autonómicos** competentes cuando la ejecución sea autonómica.
4. **Solo en último nivel**: artículos de despachos, consultoras, foros o "expertos".

Las fuentes secundarias sirven para **descubrir preguntas nuevas** y detectar fricciones del
mercado, nunca para dar por buena una respuesta. Una regla que pueda condicionar una
bonificación no se marca como fiabilidad alta hasta validarla contra fuente oficial.

## Cada respuesta necesita fecha y ejercicio

Nada de "respuesta actual" sin dimensión temporal. La forma correcta de guardar una regla es
"vigente para el ejercicio 2026", "vigente desde 2026-01-01", "pendiente de confirmar para
2027". Es especialmente crítico en las disposiciones **anuales**, como la Resolución del SEPE
sobre aula virtual y plazos de comunicación.

## Cuándo toca revisión extraordinaria

Cualquiera de estos eventos obliga a repasar la base sin esperar al repaso periódico:

- Nueva Ley de Presupuestos que pueda afectar al crédito.
- Modificación de la Ley 30/2015 o del RD 694/2017.
- **Resolución anual del SEPE** (la de aula virtual/plazos caduca con el ejercicio).
- Nueva versión de la aplicación de Formación Programada.
- Cambios en el Sistema RED o en la TGSS (afecta a PRO-15, casilla 763).
- Nuevas guías u orientaciones de costes de FUNDAE.
- Cambios en formularios o modelos.
- Criterios administrativos o judiciales sobre inspección y reintegros.

Flujo: monitorizar BOE/SEPE/FUNDAE/TGSS → ¿hay cambio? → localizar las Q&A afectadas →
comparar respuesta antigua y nueva → revisión jurídica → actualizar vigencia y fiabilidad →
publicar → **conservar el histórico**. Si no hay cambio, revisión periódica de fuentes y
enlaces, marcando los obsoletos.

## "No especificado" nunca es un hueco en blanco

Debe indicar cuál de estas cuatro cosas pasa (mismos códigos que usa [[04-documentacion-custodia]]):

- `no_localizado_en_fuente_oficial`
- `depende_del_caso`
- `depende_de_normativa_autonomica`
- `pendiente_de_norma_ejercicio`

Sin el motivo, un modelo de IA lee la ausencia de dato como "no existe obligación", que es
justo el error más caro de esta materia.

## Doble revisión para lo que está por debajo del 90 %

Toda respuesta con fiabilidad inferior al 90 % necesita una segunda revisión humana antes de
usarla para automatizar una decisión económica. Las que más lo merecen, según la propia
investigación de origen:

- IVA y fiscalidad del coste (CRE-16).
- Compatibilidad con ayudas concretas (AYU-03).
- Formación obligatoria sectorial: PRL, igualdad, compliance (LEG-04).
- Efectos particulares de determinados ERTE (PAR-05).
- Límites económicos que puedan cambiar por norma anual (CRE-08).
- Reglas autonómicas sobre aula virtual (MOD-05).

## Separar la respuesta de la evidencia

Una misma pregunta puede apoyarse en varios artículos y varias FAQ. Si la fuente cambia, la
respuesta debe poder recalcularse sin editar a mano docenas de fichas. Por eso conviene
conservar aparte, por cada regla: norma, artículo, versión, fecha de consulta y el fragmento
de evidencia. En esta base eso vive en `normativa/*.md` (texto literal verificado) y el índice
está en [[11-fuentes]]; las fichas 01–08 solo llevan el resumen y la columna de fuente.

## Alertas automáticas que debería poder disparar

Si alguna vez esta base pasa de fichas a tabla consultable, estas combinaciones deberían
levantar aviso solas — se corresponden una a una con áreas sujetas a comprobación o
responsabilidad (ver [[05-auditoria-sanciones-fraude]]):

bonificación superior al coste · curso sin evidencia de asistencia · proveedor que debería
estar inscrito sin registro asociado · inicio comunicado fuera de plazo · participante por
debajo del 75 % · organización externalizada sin contrato · costes de organización por encima
del límite · artículos o regalos imputados al curso · ausencia de cuenta contable diferenciada.

## Si algún día hay que exportarla

La decisión de fondo no es elegir formato, sino asumir que esto es una **base temporal de
conocimiento normativo**: una misma pregunta tiene distintas respuestas según el ejercicio, el
ámbito territorial, el rol del actor y la versión de la norma. El régimen de 2026 lo demuestra.

Arquitectura recomendada en el documento de origen: **SQL** como repositorio canónico, **JSON**
para API/RAG/LLM y **CSV** como exportación operativa (Excel, auditoría, intercambio). En CSV,
una fila debe representar **una versión de una respuesta**, no una pregunta, con los multivalor
separados por `|` y en UTF-8; si no, la respuesta de 2026 pisa la de 2025 y se pierde la
trazabilidad.

Campos mínimos por pregunta: `qa_id`, `categoria`, `subcategoria`, `stakeholder`, `pregunta`,
`pregunta_normalizada`, `respuesta_corta`, `respuesta_ampliada`, `no_especificado`,
`motivo_no_especificado`, `fiabilidad_pct`, `nivel_evidencia` (BOE / organismo oficial / guía
oficial / secundaria / inferencia), `riesgo`, `rol_afectado`, `ambito_territorial`, `ejercicio`,
`vigente_desde`, `vigente_hasta`, `norma_principal`, `articulo`, `source_ids`,
`fecha_verificacion`, `estado`, `keywords`, `version`, `reviewer`, `change_reason`.

Las fuentes van en su **propia tabla** (`sources`: tipo, organismo, título, referencia legal,
fecha de publicación, vigencia, URL, `checked_at`, estado) y se relacionan con las preguntas por
una tabla intermedia `qa_sources` con el artículo concreto y el papel de esa evidencia.
