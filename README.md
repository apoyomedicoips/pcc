# PCC – Formulario embebido en GitHub Pages

Este repositorio publica el **Formulario de Licencia y/o Permiso** embebido desde una **Web App de Google Apps Script**.

## 1) Despliega la Web App en Apps Script

1. En tu proyecto de Apps Script (el que contiene `Code.gs`, `Index.html`, `Print.html`):
   - Menú **Deploy** → **Manage deployments** → **New deployment**.
   - Tipo: **Web app**.
   - **Execute as**: *Me*.
   - **Who has access**: *Anyone with the link*.
   - Guardar y copia la **URL** (termina en `/exec`).

2. Asegúrate de que en `doGet()` tengas `setXFrameOptionsMode(HtmlService.XFrameOptionsMode.ALLOWALL)` (ya viene en tu código) para permitir el embebido.

## 2) Publicar en GitHub Pages

### Opción A: raíz del repositorio
1. Deja `index.html` y `.nojekyll` en la **raíz** del repo.
2. En `index.html`, reemplaza:
   ```js
   const WEB_APP_URL = 'https://script.google.com/macros/s/AKfycbyL11Rgc-oQeFI2GgUfG9s0Bs42V8cjqA-SylCyE7RRqr0ShfIDZEnur3ituyQou-NYFQ/exec';
