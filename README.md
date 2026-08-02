# Relojes Streat Lab

Carpeta pública que SOLO contiene los relojes (horarios) de los robots del ERP.
Los minutos de GitHub Actions son gratis e ilimitados en repositorios públicos:
por eso los relojes viven aquí.

- El CÓDIGO de los robots sigue en el repositorio privado `Streatlab/binagre`
  (cada reloj entra con una llave de solo lectura, secreto `GH_PAT`).
- Las CONTRASEÑAS de plataformas no están aquí: viven en la tabla
  `robot_credenciales` del ERP y cada reloj las pide en el momento con el
  secreto `SUPABASE_SERVICE_ROLE_KEY`.
- El HORARIO no está escrito a fuego: cada reloj de servicio consulta la
  tabla `horario_local` de la configuración del ERP antes de correr.

Aquí no hay datos, ni ventas, ni clientes, ni claves.
