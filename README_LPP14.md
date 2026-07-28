# 🏗️ Dashboard interactivo · Arranque de la línea LP‑P14

**Instructivo interactivo para arrancar la Línea de Postes Calibre 14 (LP‑P14), de la cinta de acero al poste terminado.**

Aplicación web autocontenida que convierte el procedimiento de arranque en una guía visual navegable: recorre las **6 fases** y los **23 pasos** de la línea, con el tablero de cada estación **simulado y encendiéndose según el paso**, herramientas, cuidados críticos de seguridad y espacio para foto y video en cada paso.

> Proyecto de trabajo estandarizado y transferencia de conocimiento. Ingeniería Industrial, seguridad, poka‑yoke y estandarización de arranque de línea.

![Hecho con](https://img.shields.io/badge/Hecho_con-Claude_AI-8A2FC9)
![Tipo](https://img.shields.io/badge/Tipo-SOP_digital_interactivo-1A4088)
![Alcance](https://img.shields.io/badge/Alcance-6_fases_·_23_pasos-2E6BE6)
![Formato](https://img.shields.io/badge/Formato-HTML_autocontenido-333)
![Seguridad](https://img.shields.io/badge/Seguridad-EPP_anticorte_+_poka--yoke-A2503C)

---

## 🎯 El problema

Arrancar la línea LP‑P14 es un proceso **largo, delicado y peligroso** que dependía de conocimiento no documentado.

El arranque cruza varias estaciones —desbobinadora, prensa/troquel, controlador de corte a medida ais III, guillotina— cada una con su **propio tablero** de botones, perillas y selectores. Un error de secuencia no solo tira producción: hay pasos con **riesgo real de lesión** (cargas suspendidas con grúa, láminas bajo tensión que salen disparadas, dedos entre cintas de acero).

Toda esa lógica vivía en la experiencia de unas pocas personas y en un Excel de proceso. No existía una forma **visual, segura y estandarizada** de enseñar el arranque ni de documentar que cada paso se hizo bien.

| Problema | Descripción |
|---|---|
| **Dependencia de expertos** | El arranque completo solo lo dominaban unas pocas personas. |
| **Múltiples tableros distintos** | Cada estación tiene su HMI; es fácil equivocar botón o secuencia. |
| **Riesgo de seguridad** | Grúa, cintas a tensión y corte: errores que lastiman, no solo retrasan. |
| **Sin estandarización visual** | El know‑how estaba en un Excel y en la cabeza de los operadores. |

---

## 💡 La solución

Un **instructivo interactivo** (SOP digital) que traduce el Excel de proceso en una experiencia guiada, visual y a prueba de errores.

1. El operador abre el dashboard en cualquier navegador; **no instala nada**.
2. Elige una de las **6 fases** desde una línea de tiempo tipo tablero de proyecto.
3. Avanza paso a paso: en cada uno, el **tablero de la estación se enciende** y resalta el control exacto que hay que tocar.
4. Ve la **herramienta**, la **explicación simple** y el **cuidado / error común (poka‑yoke)**; los pasos críticos de seguridad están marcados.
5. Puede **adjuntar foto y video** de cada paso y guardar todo dentro del propio archivo HTML para distribuirlo.

El resultado: cualquier operador entiende y practica el arranque completo de la línea, con la seguridad y la secuencia correctas, **sin depender de que un experto esté disponible**.

---

## 🔄 Antes / Después

Comparación cualitativa en lo que de verdad cambió. Sin métricas inventadas.

| Dimensión | Antes | Después |
|---|---|---|
| Fuente del conocimiento | Excel de proceso + experiencia personal | Guía visual interactiva de las 23 pasos |
| Forma de enseñar | Acompañar al experto en el arranque real | Recorrido guiado, tablero por tablero |
| Seguridad | Los cuidados se aprendían con el tiempo | Cuidados críticos marcados en cada paso |
| Documentación | Informal o inexistente | Casillas a documentar y foto/video por paso |
| Estandarización | Cada quien arrancaba a su manera | Una sola secuencia correcta para todos |

---

## ⭐ Por qué importa

El valor no está en la interfaz, sino en volver el arranque **seguro, transferible y estandarizado**:

- **Seguridad primero:** los pasos de mayor riesgo (grúa, cintas a tensión, corte) llevan advertencia explícita antes de ejecutarse.
- **Trabajo estandarizado:** todos siguen la misma secuencia, con las mismas herramientas y los mismos cuidados.
- **Poka‑yoke:** cada paso incluye el error común y cómo evitarlo, reduciendo scrap y paros.
- **Continuidad operativa:** el arranque deja de depender de una sola persona; se puede formar a alguien nuevo sin frenar la línea.
- **Trazabilidad:** las casillas a documentar y la foto/video dejan evidencia de que el arranque se hizo bien.

---

## 🔁 Cómo funciona

Un hub con línea de tiempo lleva a cada fase; dentro de cada fase, un renderizador dibuja el tablero real de la estación y lo enciende paso a paso.

```mermaid
flowchart LR
    A[Cinta de acero Cal. 14] --> F1[01 · Montaje de la cinta]
    F1 --> F2[02 · Cambio de troquel]
    F2 --> F3[03 · Desbobinadora]
    F3 --> F4[04 · Configuración ais III]
    F4 --> F5[05 · Prensa & Guillotina]
    F5 --> F6[06 · Calidad & Control]
    F6 --> Z[Poste terminado]
```

| Componente | Tecnología | Rol |
|---|---|---|
| Construcción | **Claude AI** (artifact interactivo) | Genera el dashboard a partir del Excel de proceso |
| Interfaz | HTML + CSS (diseño editorial estilo consultoría) | Hub, fases y navegación con acento por fase |
| Tableros simulados | Renderizador propio en JavaScript | Dibuja y enciende la HMI de cada estación por paso |
| Foto / video | Drag & drop + IndexedDB (`LP14Media`) | Evidencia por paso, persistente en el navegador |
| Distribución | "Guardar todo en el HTML" (media *baked*) | Exporta un archivo único autocontenido |

---

## 🗂️ Las 6 fases del arranque

| # | Fase | Alcance | Enfoque |
|---|---|---|---|
| **01** | Montaje de la cinta | Pasos 1 – 7 | Montar el rollo en la desbobinadora y llevar la cinta a corte *(4 cuidados críticos)* |
| **02** | Cambio de troquel | 8 pasos | Limpiar, montar y alinear el troquel; ajustar punzones según SKU |
| **03** | Desbobinadora | 6 pasos | Operar el tablero: velocidad, sentido y modo para alimentar la línea |
| **04** | Configuración | Pasos 9 – 13 | Cargar largo, punzones y alimentadas en el tablero **ais III** |
| **05** | Prensa & Guillotina | Mov. del paso 14 | Bajar el troquel, cortar el tramo defectuoso y automatizar el ciclo |
| **06** | Calidad & Control | Pasos 15 – 23 | Verificar contra muestras, automatizar la línea y cerrar el turno |

Cada paso trae: **acción**, **explicación simple**, **herramienta/equipo**, y un **cuidado / error común** en lenguaje universal, pensado para que lo entienda cualquiera.

> **EPP obligatorio en todo momento:** guantes anticorte + mangas anticorte.

---

## 🚀 Instalación y uso

**Requisitos:** solo un navegador moderno (Chrome, Edge, Firefox). No requiere internet ni instalación; es un único archivo HTML autocontenido.

1. Abre **`LPP14 Arranque · Dashboard standalone.html`** con doble clic.
2. En el hub, **toca una fase** de la línea de tiempo.
3. Recorre los pasos con **Anterior / Siguiente**; observa cómo se enciende el control en el tablero.
4. Adjunta **foto o video** en cada paso arrastrándolos al recuadro.
5. Usa **"Guardar todo en el HTML"** para exportar una copia con las fotos y videos incrustados.

> Las fotos y videos se guardan en el navegador (IndexedDB). Para conservarlos de forma permanente o compartirlos, usa "Guardar todo en el HTML" y distribuye ese archivo.

---

## ⚠️ Limitaciones y mejoras futuras

- **Fotos/videos por capturar:** la estructura está lista; falta poblar cada paso con el material real de piso.
- **Persistencia local:** la evidencia vive en el navegador hasta que se hornea en el HTML. Mejora futura: exportar también a PDF de una sola pasada.
- **Un solo producto:** hoy cubre el arranque de la LP‑P14 (postes Cal. 14). Mejora futura: perfiles por SKU / calibre.
- **Verificación en piso:** validar la secuencia y los cuidados con los operadores expertos antes de oficializarlo como SOP.

---

## 💼 Stack

`Claude AI` · `HTML` · `CSS` · `JavaScript` · `IndexedDB` · `SOP digital` · `HMI simulada`

---

## 👤 Autor

**Carlos G. Dumas.** Estudiante de Ingeniería Industrial, Tecnológico de Monterrey. Operaciones, manufactura, mejora de procesos y automatización operativa.

Contacto: cgarciadumas@gmail.com
