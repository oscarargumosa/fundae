# Índice de fuentes: qué es cada norma, dónde está y qué mirar en ella

Ver [[00-resumen-ejecutivo]] y [[10-mantenimiento]]. Cuando cites una regla, cita de aquí: el
texto literal verificado está en `normativa/*.md`, y esta ficha dice cuál abrir.

## Normas (BOE)

| Identificador BOE | Norma | Fichero con el texto | Para qué se usa |
|---|---|---|---|
| BOE-A-2015-9734 | Ley 30/2015, de 9 de septiembre, del Sistema de Formación Profesional para el Empleo en el ámbito laboral | `normativa/ley-30-2015.md` | Iniciativas, formación programada, crédito, cofinanciación (art. 9.5), entidades, control y responsabilidades. Modificada por la Ley 3/2023 y afectada por la LO 3/2022. |
| BOE-A-2017-7769 | RD 694/2017, de 3 de julio, que desarrolla la Ley 30/2015 | `normativa/rd-694-2017-consolidado.md` | Crédito, RLT (15 días), costes, módulos (art. 16), cofinanciación (art. 17), comunicaciones y bonificaciones (art. 18). **Texto consolidado**, actualizado a 31-dic-2025. |
| BOE-A-2025-27115 | RD 1189/2025, de 26 de diciembre | `normativa/rd-1189-2025.md` | Nueva redacción de los arts. 18 y 25 y la DT 2.ª del RD 694/2017: plazo límite de bonificación, comprobación, reintegro y devolución voluntaria. BOE núm. 315, de 31-dic-2025. **En vigor desde el 1-ene-2026.** |
| BOE-A-2025-25790 | Resolución del SEPE de 25 de noviembre de 2025 | `normativa/resolucion-sepe-aula-virtual-2026.md` | Ejercicio **2026**: aula virtual síncrona como presencial, bimodalidad ("aula espejo"), trazabilidad de conexiones, comunicación de inicio a dos días, medios electrónicos. BOE núm. 301, de 16-dic-2025. |
| BOE-A-2000-15060 | RDL 5/2000 (LISOS) | `normativa/lisos-rdl-5-2000.md` | Tipificación y cuantía de infracciones y sanciones; falseamiento y simulación como muy graves; exclusión de beneficios. |
| — | Orden TAS/2307/2007, de 27 de julio | (no descargada) | Crea el sistema telemático de comunicación. Relevancia transitoria; la Resolución de 2026 remite a su art. 9 para la comunicación de la declaración responsable. |

## Fuente operativa (no normativa)

| Fuente | Fichero | Qué contiene |
|---|---|---|
| FUNDAE — FAQ, guías y orientaciones de costes | `normativa/fundae-faq-oficial.md` | Criterios operativos: 75 % de finalización, 30/80 participantes, dos meses para el diploma, límites de costes, casilla 763 del Sistema RED, crédito mínimo de microempresas. Consultado el 3-sep-2026. |

**Cuidado con lo que FUNDAE NO dice.** No es una norma con artículos: sus FAQ y sus PDFs son
orientativos. Y hay un caso concreto que conviene tener presente al responder: los módulos
económicos en €/hora/participante que circulan por internet corresponden a la **oferta
formativa de convocatorias públicas**, no a la formación programada bonificada, que se
justifica por **coste real con factura**. Está documentado en `normativa/fundae-faq-oficial.md`.

## Enlaces oficiales

- Ley 30/2015 — https://www.boe.es/buscar/doc.php?id=BOE-A-2015-9734
- RD 694/2017 (consolidado) — https://boe.es/buscar/act.php?id=BOE-A-2017-7769
- RD 1189/2025 — https://www.boe.es/diario_boe/txt.php?id=BOE-A-2025-27115 · ELI: https://www.boe.es/eli/es/rd/2025/12/26/1189
- Resolución SEPE 25-nov-2025 — https://www.boe.es/diario_boe/txt.php?id=BOE-A-2025-25790
- LISOS — https://www.boe.es/buscar/act.php?id=BOE-A-2000-15060
- FUNDAE, entidades organizadoras — https://www.fundae.es/empresas/entidades-organizadoras-y-de-formaci%C3%B3n/entidades-organizadoras
- FUNDAE, ejercicio 2026 (aplicación de formación programada) — https://www.fundae.es/actualidad/noticias/2025/12/11/ejercicio-2026--aplicaci%C3%B3n-de-formaci%C3%B3n-programada-por-las-empresas

## Cómo leer la columna "Fuente" de las fichas 01–08

- **Ley 30/2015 · RD 694/2017 · RD 1189/2025 · Resolución SEPE · LISOS** → norma. Se puede
  citar como regla cerrada, indicando el artículo cuando la ficha lo dé.
- **FUNDAE · FAQ FUNDAE · Guías FUNDAE · Orientaciones de costes** → criterio operativo
  oficial. Es lo que aplica FUNDAE en la práctica, pero puede cambiar por ejercicio o por
  versión de la aplicación: no tiene rango de norma.
- **Inferencia** → no hay fuente directa; es una deducción de esta base a partir de las
  obligaciones legales. Dilo así al responder, y nunca la des como cerrada.
- **No localizada en fuentes oficiales revisadas** → se buscó y no se encontró. No equivale a
  "no existe obligación": ver los cuatro motivos de "No especificado" en [[10-mantenimiento]].
