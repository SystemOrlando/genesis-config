# Configuración de GÉNESIS

<div align="justify">

El catálogo de conectores que la app descarga al abrir, en lugar de llevarlo entero en el instalador. Así se actualiza
sin publicar una versión nueva, y la lista no viaja en el ejecutable.

</div>

- **`catalogo.json`** tiene `{ "destacados": [...], "abiertos": [...] }` con el formato de `EntradaCatalogo` de la app.
- La app lo lee de `GENESIS_CONFIG_URL` (por defecto, el `catalogo.json` de este repositorio en GitHub).
- Si el servidor no responde, la app usa su **copia local incrustada**: sigue mostrando conectores sin internet.

## Cómo publicarlo

1. Crea el repositorio público `SystemOrlando/genesis-config` en GitHub.
2. Sube este `catalogo.json`. La app lo tomará de `raw.githubusercontent.com` automáticamente.
3. Para usar tu propio servidor, pon su URL en `.env` como `GENESIS_CONFIG_URL=` antes de compilar.

## Qué NO está aquí, a propósito

<div align="justify">

Las instrucciones del agente (cómo piensa y actúa) se quedan en la app: moverlas a un servidor haría que GÉNESIS no
pudiera dar órdenes sin internet, y ya están en Rust compilado, que es difícil de leer.

</div>
