# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

A Hebrew-language calculator web app (מחשבון) — a single-page, no-build, vanilla HTML/CSS/JS project. Open `index.html` directly in a browser; no server or build step is required.

## Architecture

All application code lives in `index.html` as a self-contained file:

- **Styling**: Tailwind CSS loaded from CDN with a custom Material Design 3-inspired color palette configured inline via `tailwind.config`. RTL layout (`dir="rtl"`, `lang="he"`).
- **Icons**: Google Material Symbols Outlined via CDN.
- **Calculator logic**: IIFE at the bottom of `<body>` using `data-value`, `data-op`, and `data-action` attributes to wire up button events. State is held in four variables: `current`, `previous`, `operator`, `overwriteCurrent`.
- **Display**: Two elements — `#calc-display` (main result) and `#calc-expression` (secondary expression string).
- **Side drawer**: Static HTML for a nav drawer (History, Settings, Scientific mode) — currently UI-only with no backing logic.

`stitch-export/calculator/calculator.html` is a static design export (no JS wiring) used as a visual reference/mockup.

`index.html` adds `.calculator-scale` (`zoom: 0.5`) on top of the stitch-export layout for embedding/preview purposes — the stitch-export does not have this wrapper.
