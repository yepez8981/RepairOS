# Static Site (Netlify/Vercel) conectado a GAS

- `index.html` y `sign.html` conservan tu JavaScript original pero ahora usan un polyfill que convierte
  `google.script.run.<fn>(...)` en llamadas `fetch` a tu Web App de Google Apps Script.
- `label.html` es un puente: pide a GAS la URL pública de la etiqueta y redirige.

## Variables
- Cambia la constante `GAS_EXEC` (arriba de cada HTML) si actualizas tu deployment de Apps Script.

## Flujo de etiqueta
- Espera que exista en tu Code.gs una función `getLabelPublicUrl(orderId)` que devuelva `{ labelUrl: "https://..." }`.
  Si ya generás esa URL al crear la orden, solo haz que esta función la re-calculé o busque y la retorne.
