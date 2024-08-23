# Unofficial LaTeX Templates following the RPTU Kaiserslautern-Landau Corporate Design

Some first LaTeX templates for the new RPTU. Non official and always work in progress.
A similar presentation has also recently been developed by Patrick Mischke (https://github.com/Patschke/RPTU-Design) together with some poster template.


## A Minimal Beamer Presentation

A minimal presentation without navigation bar and with main color **RPTU dunkelblau**. The second highlight color will be automatically set to **RPTU hellblau**. The total number of slides is written in the footline as well as the short name, the short institute and the short title.

```latex
\documentclass{beamer}
\usepackage[T1]{fontenc}

% load RPTU theme with some options
\usetheme[dunkelblau,
		  redhattext=true,
		  displayinstitute,       
		  displayframetotal
		  ]{rptu}

\title[Short Title in Foot]{The complete title for the title page}
\subtitle{a subtitle for the title page}
\date{Kaiserslautern, January 5th, 2023}
\author[Short Name]{Full Name}
\institute[Short Institute]{Full Affiliation}

% info for thank you page
\thankstitle{Thank you title}
\thankssubtitle{content of thanks subtitle}
\thanksinfo{and other info as needed}

% non default logos (optional)
\renewcommand{\ownlogo}{}  % fill with logo file from logo generator
\renewcommand{\sponsorlogo}{} % fill with sponsor logos

% content
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

\rptuthankyou % creates the thank you page

\end{document}
```

## Available Options For Beamer Theme RPTU

```latex
\usetheme[dunkelblau,
          %hellblau, rot, orange, dunkelgruen, hellgruen, blaugrau, gruengrau, violett, pink,
          redhattext=false, %redhattext=true,
          ownlogo=false, %ownlogo=true,
          sponsorlogo=false, %sponsorlogo=true,
          frametotal=false, %frametotal=true,
          %hideframetotal, displayframeetotal
          institute=false, %institute=true,
          %hideinstitute, displayinstitute,
          navigation=false, %navigation=true,
          %hidenavigation, displaynavigation,
          compress]{rptu}
```

| Option | Description |
| ---------|------------|
| dunkelblau | Sets the main color of the presentation to **RPTU Dunkelblau**. <br> The options hellblau, rot, orange, dunkelgruen, hellgruen, blaugrau, gruengrau, violett, pink <br> work analogously. |
| redhattext=true | Use Red Hat Text as main font |
| redhattext=false | Use Arial (XeLaTeX, LuaLaTeX) or Computer Modern as main font |
| ownlogo=true | Replace Default RPTU logo with one from the logo generator|
| ownlogo=false | Keep RPTU default logo |
| sponsorlogo=true | Place a sponsor logo in upper right corner |
| sponsorlogo=false | Do not use a sponsor logo|
| displayframetotal, frametotal=true | Show the slide number as current slidenumber/total slide number|
| hideframetotal, frametotal=false| Show the slide number as current slidenumber|
| displaynavigation, navigation=true | Show the navigation in the headline (mini frames layout)|
| hidenavigation, navigation=false| Do not include any navigation |
| displayinstitute, institute=true | Show the short institute/affiliation name in the footline|
| hideinstitute, institute=false| Do not include the institute in the footline |
| compress| Same as beamer's compress, e.g. one-line navigation mini-frames|

## Available Frame Styles

- plain (beamer's plain)
- minimal: only slide number and short RPTU logo in footline
- highlight1: background of slide in main color and some color changes for contrast
- highlight2: background of slide in secondary color (other color of the allowed color combinations) and some color changes for contrast
- black: background of slide is black, font are in white

## TODOs

- [ ] navigation bar when not using compress (-> positioning of multiline navigation dots, height of headline)
- [ ] navigation bar option: only sectionnames, no mini frames

## Notes

If you want to use Red Hat Text, make sure that the static versions of the font are installed on your system. Since we use the package fontspec to load Red Hat Text you cannot compile with pdflatex.
