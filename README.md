# Cursus Honorum

> Plantilla LaTeX de Currículum Vítae de orientación académica y humanista, concebida para profesionales con trayectorias densas en docencia universitaria, investigación, consultoría y formación posgradual.

[![LaTeX](https://img.shields.io/badge/LaTeX-pdfLaTeX-008080?logo=latex&logoColor=white)](https://www.latex-project.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Compatible](https://img.shields.io/badge/Compatible-MiKTeX%20%7C%20TeX%20Live%20%7C%20Overleaf-brightgreen)](#instalación)
[![Version](https://img.shields.io/badge/Version-1.0-orange)]()

---

## Tabla de Contenidos

1. [Características](#características)
2. [Captura del Resultado](#captura-del-resultado)
3. [Estructura del Documento](#estructura-del-documento)
4. [Instalación](#instalación)
5. [Uso Rápido](#uso-rápido)
6. [Personalización](#personalización)
7. [Resolución de Problemas](#resolución-de-problemas)
8. [Contribuciones](#contribuciones)
9. [Licencia](#licencia)
10. [Créditos y Atribución](#créditos-y-atribución)
11. [English Version](#english-version)

---

## Características

| Característica | Descripción |
|----------------|-------------|
| Tipografía | Palatino vía `mathpazo`, con afinamiento de `microtype` |
| Paleta | Tres colores configurables en el preámbulo |
| Iconografía | `fontawesome5` con fallback automático si no está instalado |
| Idioma | Español (con `babel`); adaptable a otros idiomas |
| Compilador | `pdflatex` (compatible también con `lualatex` y `xelatex` con ajustes mínimos) |
| Hipervínculos | Activos y coloreados con `hyperref` |
| Estructura | Secciones definidas manualmente, sin dependencia de `titlesec` |
| Tablas | `tabularx` para repartición automática del ancho |
| Listas | `enumitem` para control fino del espaciado |
| Multicolumna | `multicol` para listados densos en tres columnas |

## Captura del Resultado

![Vista previa de Cursus Honorum](preview.png)

> Para incorporar la captura, sustituya `preview.png` por un PDF compilado de la plantilla convertido a imagen mediante `pdftoppm cursus-honorum.pdf preview -png -r 150`.

## Estructura del Documento

La plantilla se articula en siete secciones, cada una optimizada para un tipo de información específico:

1. **Encabezado**: nombre, títulos académicos, datos de contacto con iconografía.
2. **Perfil Profesional**: resumen narrativo de la trayectoria (60-100 palabras).
3. **Habilidades**: bloque categorizado mediante `description` (idiomas, software, gestión, comunicación).
4. **Experiencia Profesional**: subsecciones temáticas con tres patrones tipográficos según el tipo de información (tabla compacta, listado tricolumnar, descripción extensa).
5. **Educación y Formación Académica**: tabla cronológica con marca distintiva para programas en curso.
6. **Reconocimientos**: distinciones y premios recibidos.
7. **Certificaciones Complementarias**: cursos, diplomas y formación continua.

## Instalación

### Opción 1: Overleaf

1. Descargue el archivo `cursus-honorum.tex` desde [el repositorio](https://github.com/girebz/Plantilla-CV-CursusHonorum).
2. Inicie sesión en [Overleaf](https://www.overleaf.com).
3. Cree un nuevo proyecto desde "New Project > Upload Project".
4. Suba el archivo `.tex`.
5. Compile con el botón "Recompile". Overleaf instalará automáticamente todos los paquetes requeridos.

### Opción 2: Instalación local (Linux, macOS, Windows)

**Requisitos previos:**

- Una distribución LaTeX completa: [TeX Live](https://www.tug.org/texlive/) (Linux/macOS) o [MiKTeX](https://miktex.org/) (Windows).
- Un editor LaTeX: [TeXstudio](https://www.texstudio.org/), [VSCode con LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop), o cualquier otro de su preferencia.

**Pasos:**

```bash
git clone https://github.com/girebz/Plantilla-CV-CursusHonorum.git
cd Plantilla-CV-CursusHonorum
pdflatex cursus-honorum.tex
```

MiKTeX solicitará la instalación automática de paquetes ausentes durante la primera compilación. TeX Live, en su versión completa (`texlive-full` en Debian/Ubuntu), incluye todos los paquetes requeridos por defecto.

### Paquetes requeridos

```
inputenc, fontenc, babel, hyphenat, microtype, mathpazo, geometry,
xcolor, enumitem, multicol, ragged2e, array, tabularx, parskip,
hyperref, fontawesome5
```

## Uso Rápido

1. Abra el archivo `cursus-honorum.tex` en su editor.
2. Localice los puntos marcados con el comentario `% [EDITAR]` en el preámbulo y el cuerpo del documento.
3. Sustituya los datos de ejemplo por los suyos.
4. Compile con `pdflatex cursus-honorum.tex` (dos pasadas si emplea referencias cruzadas).
5. El archivo `cursus-honorum.pdf` resultante contiene su currículum.

### Eliminación de secciones completas

Para suprimir una sección entera, comente todo el bloque correspondiente con el carácter `%` al inicio de cada línea, o bien envuélvalo en un comentario de bloque mediante el paquete `verbatim`:

```latex
\usepackage{verbatim}
% ...
\begin{comment}
\section{Sección a Suprimir}
... contenido ...
\end{comment}
```

### Reordenación de secciones

Las secciones son independientes entre sí; su orden puede modificarse cortando y pegando los bloques `\section{...}` correspondientes.

## Personalización

### Cambio de paleta cromática

Los tres colores principales se definen en el preámbulo:

```latex
\definecolor{acento}{HTML}{1F3A5F}      % Azul marino (jerarquías, enlaces)
\definecolor{gris}{HTML}{4A4A4A}         % Gris medio (subsecciones)
\definecolor{grisclaro}{HTML}{B0B0B0}    % Gris claro (reglas tenues)
```

Sustituya los valores hexadecimales para adaptar la paleta. Algunas combinaciones probadas:

| Estilo | Acento | Gris | Gris Claro |
|--------|--------|------|------------|
| Clásico (por defecto) | `1F3A5F` | `4A4A4A` | `B0B0B0` |
| Académico verde | `2D4A2D` | `4A4A4A` | `B0B0B0` |
| Borgoña | `6B1F2D` | `4A4A4A` | `B0B0B0` |
| Monocromo | `2C2C2C` | `5A5A5A` | `B0B0B0` |

### Cambio de tipografía

Para sustituir Palatino por otra serif, comente la línea `\usepackage{mathpazo}` y descomente alguna de estas alternativas:

```latex
% \usepackage{libertine}        % Linux Libertine
% \usepackage{ebgaramond}        % EB Garamond
% \usepackage{kpfonts}           % Kp-Fonts
% \usepackage{charter}           % Charter
```

Para cambiar a sans-serif:

```latex
\usepackage{helvet}
\renewcommand{\familydefault}{\sfdefault}
```

### Ajuste de márgenes

Modifique los valores en el bloque `\usepackage[...]{geometry}`:

```latex
\usepackage[left=1.5cm,right=1.5cm,top=1.2cm,bottom=1.4cm]{geometry}
```

### Adaptación a otros idiomas

Sustituya la opción de `babel`:

```latex
\usepackage[english]{babel}      % Inglés
\usepackage[french]{babel}        % Francés
\usepackage[portuguese]{babel}    % Portugués
\usepackage[italian]{babel}       % Italiano
```

## Resolución de Problemas

### El paquete `fontawesome5` no se instala

La plantilla incluye un fallback automático: si el paquete no está disponible, los iconos se sustituyen por etiquetas textuales («Email:», «Tel:», etcétera). El documento compila igualmente. Para instalar manualmente: `tlmgr install fontawesome5` (TeX Live) o desde el MiKTeX Console (Windows).

### Aparece advertencia sobre `inputenc`

El mensaje «inputenc package ignored with utf8 based engines» es inocuo en distribuciones LaTeX modernas (2018+), que asumen UTF-8 por defecto. No afecta al PDF resultante. Para suprimirlo, comente la línea `\usepackage[utf8]{inputenc}`.

### Un bloque de texto se desborda en el margen derecho

Verifique que las URL largas se incluyan dentro de `\href{...}{...}` para que `hyperref` las gestione correctamente. Si el problema persiste con texto regular, divida el párrafo o reduzca su longitud; si es estructural, ajuste los márgenes en `geometry`.

### La compilación falla con errores en `\section`

Verifique que no se haya cargado el paquete `titlesec` en alguna modificación posterior. La plantilla redefine `\section` y `\subsection` manualmente y es incompatible con `titlesec`.

## Contribuciones

Si desea proponer mejoras:

1. Realice un *fork* del repositorio en [github.com/girebz/Plantilla-CV-CursusHonorum](https://github.com/girebz/Plantilla-CV-CursusHonorum).
2. Cree una rama temática: `git checkout -b feature/nombre-de-la-mejora`.
3. Comprométa los cambios: `git commit -am 'Añade característica X'`.
4. Envíe la rama: `git push origin feature/nombre-de-la-mejora`.
5. Abra un *pull request* describiendo la motivación y el alcance del cambio.

Áreas con valor potencial para contribución: traducciones del bloque documental a otros idiomas, variantes cromáticas adicionales, ejemplos compilados con distintos perfiles profesionales (ingenieril, jurídico, sanitario), versión sans-serif optimizada.

## Licencia

Este proyecto se distribuye bajo licencia [MIT](LICENSE), que permite uso personal y comercial, modificación y redistribución, conservando el aviso de copyright original en el código fuente.

## Créditos y Atribución

**Autor original:** Giorgio Angelo Reveco Barraza
**Sitio web:** [giorgioreveco.com](https://giorgioreveco.com)
**ORCID:** [0009-0007-9553-2710](https://orcid.org/0009-0007-9553-2710)
**GitHub:** [@girebz](https://github.com/girebz)
**Repositorio:** [github.com/girebz/Plantilla-CV-CursusHonorum](https://github.com/girebz/Plantilla-CV-CursusHonorum)

### Cita académica (BibTeX)

```bibtex
@misc{reveco2026cursushonorum,
  author       = {Reveco Barraza, Giorgio Angelo},
  title        = {Cursus Honorum: Plantilla LaTeX de Curr\'iculum V\'itae Acad\'emico},
  year         = {2026},
  howpublished = {\url{https://github.com/girebz/Plantilla-CV-CursusHonorum}},
  note         = {Versi\'on 1.0}
}
```

---

## English Version

**Cursus Honorum** is a LaTeX CV template designed for academics, researchers, university lecturers, and professionals with extensive postgraduate training.

### Key Features

- Built on stable LaTeX primitives, no dependency on `titlesec`.
- Palatino typography with `microtype` refinement.
- Three-color customizable palette.
- Conditional FontAwesome icons with text fallback.
- Compatible with `pdflatex` on MiKTeX, TeX Live, and Overleaf.
- Spanish by default; adaptable to other languages via `babel`.

### Quick Start

```bash
git clone https://github.com/girebz/Plantilla-CV-CursusHonorum.git
cd Plantilla-CV-CursusHonorum
pdflatex cursus-honorum.tex
```

Or upload `cursus-honorum.tex` to [Overleaf](https://www.overleaf.com) and compile online.

### License

MIT. Personal, academic, and commercial use permitted; attribution preserved in source redistributions.

---

*Plantilla mantenida por Giorgio Reveco. Última actualización: 2026.*
