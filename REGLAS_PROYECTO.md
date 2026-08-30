# REGLAS DEL PROYECTO · STREAT LAB

Archivo único que debe leer cualquier IA (Claude, Gemini u otra) antes de tocar nada.
Copia técnica de la página Notion "HANDOFF-Gemini".

## 1 · Contexto
Dark kitchen en Puente de Vallecas (Madrid). ~19 marcas virtuales en Uber Eats, Glovo y Just Eat + tienda online propia.
Objetivo prioritario del negocio: subir venta directa para depender menos de plataformas.
Repos: `Streatlab/binagre` (ERP, rama de trabajo `trabajo`, solo `master` despliega) y `Streatlab/relojes` (robots y tareas programadas, GitHub Actions).
Proyecto satélite aislado: `Streatlab/erp-david`. Nunca mezclar con Binagre.

## 2 · Reglas que no se negocian
1. El neto de plataforma nunca se calcula a mano ni con % fijo. Sale del resolutor único del ERP, que se autocalibra con liquidaciones reales.
2. Conciliación: un cargo = una factura. Tolerancia de importe 0,00 € exacto. Nunca facturas agrupadas ni pago a 60 días.
3. Publicar a producción SOLO cuando Rubén escribe "publica". La autorización no se hereda entre tandas.
4. Vercel plan Hobby: máximo 100 despliegues al día, crons solo diarios. Todo robot frecuente vive en `relojes` (GitHub Actions), no en Vercel.
5. Antes de decir "hecho": aportar prueba verificable. Sin prueba, se dice "bloqueado".
6. Antes de decir "no existe X": comprobarlo en el repo, la base de datos o Notion. Nunca suponer.

## 3 · Robot Just Eat — qué ya está descartado
El robot vive en la nube. PROHIBIDO proponer PC local, ordenador dedicado, runner físico o proxy residencial.
Bloqueo actual: muro anti-bots de Cloudflare en el portal de acceso de Just Eat.
Ya intentado y fallido (no repetir):
1. Reutilización de cookies de sesión del navegador sigiloso.
2. Modificación de la huella digital del navegador.
3. Espera de 180 segundos al verificador de Cloudflare.
4. Navegador oculto ejecutado sobre pantalla virtual.
Notas útiles: en GitHub Actions el navegador escucha tanto en la dirección local moderna como en la clásica — hay que probar ambas. En modo oculto el verificador de Cloudflare ni siquiera aparece en la página.
Pendiente aparte: recuperar los datos desde el 14 de agosto.

## 4 · Estilo de respuesta con Rubén
No es programador. Nada de nombres de archivo, código, base de datos o comandos en el chat.
Máximo 3-5 líneas: qué hacemos, por qué importa al negocio, qué tiene que hacer él, resultado.
Los pendientes viven en Notion ("99 Claude"), no en el chat.

## 5 · Reparto Claude / Gemini (31-ago-2026)
Gemini: robot Just Eat y scraping · módulos nuevos autocontenidos · análisis de datos grandes.
Claude: conciliación y netos · APPCC y documentos imprimibles · coordinación y estado.
Cada uno un módulo entero. Nunca los dos sobre lo mismo.
