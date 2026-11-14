# Revisor

Herramienta interna de consulta. Se publica **cifrada**: el contenido íntegro
viaja dentro de un único payload AES-256-CBC con clave derivada por
PBKDF2-SHA256 (100.000 iteraciones), que el navegador descifra con Web Crypto
tras introducir la contraseña. La clave se recuerda por dispositivo en
`localStorage`, así que solo se pide la primera vez.

Es instalable como aplicación en escritorio y móvil.

## Cómo regenerar

1. Editar los ficheros de `src/` (no se suben al repositorio).
2. `powershell -ExecutionPolicy Bypass -File .\montar.ps1` (genera `index-src.html`).
3. `powershell -ExecutionPolicy Bypass -File .\build-secure.ps1 -Password "LA_CONTRASEÑA"` (genera `index.html`, lo único que se publica).
