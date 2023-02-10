# Unofficial LaTeX Templates following the RPTU Kaiserslauteren-Landau Corporate Design

Some first LaTeX templates for the new RPTU. Non official and still work in progress.

## A Minimal Beamer Presentation

A minimal presentation without navigation bar and with main color **RPTU dunkelblau**. The second highlight color will be automatically set to **RPTU hellblau**. The total number of slides is written in the footline as well as the short name, the short institute and the short title.

```latex
\documentclass{beamer}
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}

% load RPTU theme with some options
\usetheme[dunkelblau, displayinstitute, displayframetotal]{rptu}

\title[Short Title in Foot]{The complete title for the title page}
\subtitle{a subtitle for the title page}
\date{Kaiserslautern, January 5th, 2023}
\author[Short Name]{Full Name}
\institute[Short Institute]{Full Affiliation}

\renewcommand{\ownlogo}{} % in case of own logo insert here

\begin{document}
\begin{frame}
\titlepage
\end{frame}

\begin{frame}{Overview}
\tableofcontents
\end{frame}

\section{Some Section}
\rptusectionpage % custom intro to section page

\begin{frame}[plain]
Some plain frame.
\end{frame}

\begin{frame}{Some Title}
A non plain frame with title.
\end{frame}

\end{document}
```

## Available Options For Beamer Theme RPTU

```latex
\usetheme[dunkelblau,
          %hellblau, rot, orange, dunkelgruen, hellgruen, blaugrau, gruengrau, violett, pink,
          displayframettotal, %frametotal=true,
          %hideframetotal, frametotal=false,
          displayinstitute, %institute=true,
          %hideinstitute, institute=false,
          displaynavigation, %navigation=true,
          %hidenavigation, navigation=false,
          redhattext = false, %redhattext = true,
          ownlogo = false, %ownlogo = true,
          compress]{rptu}
```

| Option | Description |
| ---------|------------|
| dunkelblau | Sets the main color of the presentation to **RPTU Dunkelblau**. <br> The options hellblau, rot, orange, dunkelgruen, hellgruen, blaugrau, gruengrau, violett, pink <br> work analogously. |
| displayframetotal, frametotal=true | Show the slide number as current slidenumber/total slide number|
| hideframetotal, frametotal=false| Show the slide number as current slidenumber|
| displaynavigation, navigation=true | Show the navigation in the headline (miniframes layout)|
| hidenavigation, navigation=false| Do not include any navigation |
| displayinstitute, institute=true | Show the short institute/affiliation name in the footline|
| hideinstitute, institute=false| Do not include the institute in the footline |
| compress| Same as beamer's compress, e.g. one-line navigation mini-frames|
| redhattext = true| Use RedHatText as font, needs XeTeX or LuaLaTex|
| redhattext = false| default |
| ownlogo = true| Replace the default RPTU logo with one from th logo generator |
| ownlogo = false| default |

## Notes

If you want to use Red Hat Text, make sure that the static versions of the font are installed on your system. Since we use the package fontspec you cannot compile with pdflatex.

## TODOs

- [ ] Set default Logo and short logo in footline as SVG such that no logos are needed
- [ ] Include Red Hat Mono font
- [ ] Replacement font Arial as first substitute if Red Hat Text not available
- [ ] Fix displaynavigation when not using compress (-> positioning of multiline navigation dots)
- [ ] Add navigation bar option to only show the sectionnames instead of miniframes
- [ ] some bugs with geometry setup, check the margins for correct positioning
- [ ] Random color option
