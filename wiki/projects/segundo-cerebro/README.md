---
type: project
title: "Segundo Cerebro"
created: 2026-07-08
updated: 2026-07-08
status: active
tags:
  - project
  - para
  - segundo-cerebro
related:
  - "[[Obsidian]]"
  - "[[Claude Code]]"
  - "[[GitHub]]"
  - "[[PARA]]"
  - "[[Hot Cache]]"
  - "[[../../overview|overview]]"
  - "[[../../hot|hot]]"
  - "[[../_index|projects/_index]]"
---

# Segundo Cerebro

Navigation: [[../_index|projects/_index]] | [[../../index|index]] | [[../../overview|overview]] | [[../../hot|hot]]

Página principal del proyecto: convertir este vault en un segundo cerebro personal persistente y compuesto (compounding), usando el patrón LLM Wiki sobre Obsidian + Claude Code, organizado con metodología [[PARA]].

---

## Objetivo

Tener un único lugar donde:

- Cualquier fuente que consuma (video, libro, documento, idea suelta) se capture sin fricción.
- Claude la lea, la resuma, la conecte con lo que ya existe, y la archive.
- Pueda preguntar cualquier cosa y obtener una respuesta sintetizada y citada, no una lista de fragmentos sueltos.
- El conocimiento se acumule con cada sesión en lugar de perderse en el historial de chat.

El objetivo no es acumular notas. Es que el vault piense conmigo: cada ingesta debe dejarlo un poco más conectado que antes.

---

## Flujo: `.raw/` → `wiki/` → `hot.md` → commit → GitHub

1. **`.raw/`** — deposito la fuente sin tocarla (transcript de YouTube, PDF de un libro, documento, nota de una idea). Es de solo lectura para Claude; nunca se modifica.
2. **`wiki/`** — Claude lee la fuente completa, la discute conmigo si hace falta, y la convierte en páginas: resumen de la fuente, entidades, conceptos, y actualizaciones a las páginas ya existentes. Bajo [[PARA]], esto se archiva en `resources/`, `projects/`, o `areas/` según corresponda.
3. **`hot.md`** — al terminar cada ingesta o sesión relevante, se reescribe el caché reciente (`wiki/hot.md`, máx. ~300 palabras): qué cambió, qué está activo, qué falta.
4. **commit** — los cambios en `wiki/` (y config relevante) se confirman en git con mensajes descriptivos, revisando antes qué se incluye.
5. **GitHub** — se hace push a `origin/main` (`github.com/ivancogollos/claude-obsidian`) para tener respaldo remoto y poder trabajar desde cualquier máquina.

Cada vuelta de este ciclo deja el vault más rico que la anterior. Ver [[Hot Cache]] para el detalle del mecanismo de caché.

---

## Herramientas

- **[[Obsidian]]** — la interfaz visual: grafo de conocimiento, edición de Markdown, plugins (Dataview, Templater, Calendar, Thino, Excalidraw, Git, Memos).
- **[[Claude Code]]** — el motor: lee fuentes, escribe y mantiene las páginas del wiki, ejecuta las skills (`/wiki`, `/wiki-ingest`, `/wiki-query`, `/wiki-lint`, `/save`, `/autoresearch`, `/canvas`).
- **VS Code** — edición manual puntual de archivos y scripts cuando hace falta salir de Obsidian/Claude Code.
- **[[GitHub]]** — respaldo remoto, historial de versiones, y sincronización entre máquinas del repositorio `ivancogollos/claude-obsidian`.

---

## Carpetas principales del sistema

```
.raw/                   fuentes inmutables
├── youtube/             transcripts de video
├── libros/              extractos, resúmenes, highlights de libros
├── documentos/          PDFs, artículos, documentos varios
└── ideas/               notas sueltas, ideas propias sin fuente externa

wiki/                   conocimiento generado por Claude
├── index.md             catálogo maestro
├── hot.md               caché de contexto reciente
├── log.md               log de operaciones (append-only)
├── overview.md           resumen ejecutivo del vault
├── projects/             trabajo activo con objetivo y (a veces) fecha límite
│   └── segundo-cerebro/  esta página
├── areas/                responsabilidades continuas, sin fecha límite
├── resources/            material de referencia por tema
└── archives/             proyectos terminados / áreas cerradas, por año
```

---

## Próximos pasos

- [ ] Empezar a depositar fuentes reales en `.raw/youtube/`, `.raw/libros/`, `.raw/documentos/`, `.raw/ideas/`.
- [ ] Hacer el primer ingest real bajo PARA (`ingest [archivo]`) y confirmar que se archiva correctamente en `resources/` o en un proyecto nuevo.
- [ ] Definir las primeras áreas reales en `wiki/areas/` (ej. salud, finanzas, trabajo) según necesidad, no de antemano.
- [ ] Triar (opcional, cuando convenga) el contenido pre-PARA que quedó en `wiki/concepts/`, `wiki/entities/`, `wiki/sources/` hacia `resources/<tema>/`.
- [ ] Crear las páginas stub [[Obsidian]], [[Claude Code]], [[GitHub]] y [[PARA]] si se quiere que dejen de aparecer como enlaces no resueltos en el grafo.

---

## Relacionado

- [[../../overview|Wiki Overview]]
- [[../../hot|Hot Cache (archivo)]]
- [[../_index|Projects Index]]
- [[Hot Cache]] — concepto del mecanismo de caché reciente
- [[PARA]]
- [[Obsidian]]
- [[Claude Code]]
- [[GitHub]]
