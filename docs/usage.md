# Uso — Plantilla Data Backstage

Instrucciones para usar la plantilla dentro de Backstage:

1. Asegúrate de que Backstage tenga configurado el `scaffolder` y que soporte la versión `scaffolder.backstage.io/v1beta3`.
2. Importa o registra este `template.yaml` en el catálogo de Backstage. Puedes hacerlo añadiendo la ruta del archivo al `catalog-info.yaml` de tu sistema o importando manualmente la entidad `Template` desde la UI.
3. En la UI de Backstage ve a "Create" → "Templates" y selecciona "Plantilla Data Backstage".
4. Completa el formulario con los datos solicitados:
   - `Nombre`: identificador del componente (usado como `metadata.name`).
   - `Descripción`: texto corto que describe el componente.
   - `Owner`: equipo o grupo responsable (ej. `default/team`).
   - `Tipo de componente`: selecciona `service`, `library` o `website`.
5. Ejecuta la creación. Si tu instalación de Backstage tiene acciones configuradas, la plantilla podrá publicar el `catalog-info.yaml` y crear los artefactos necesarios.

Visualizar Docs (TechDocs):

Notas:

¿Necesito un archivo `.env`?

- No es necesario incluir un `.env` en la plantilla de Backstage. Las credenciales y secretos no deberían almacenarse en archivos que se comitan al repositorio.
- Recomendado: usar el backend de secretos integrado de Backstage (por ejemplo, Vault, Kubernetes secrets) o los secretos del proveedor (por ejemplo, GitHub repository secrets) y mapearlos en las acciones del `scaffolder` (campo `secrets` en los pasos de publicación).
- Para pruebas locales puedes usar un `.env` en tu entorno de desarrollo, pero añade dicho archivo a `.gitignore` y nunca lo comites.
- Si la plantilla necesita un secreto para publicar en GitHub, configura el secreto en tu instalación de Backstage o usa los secretos del proveedor y referencia su nombre en el paso `publish:github`.

Si quieres, puedo añadir un ejemplo de `catalog-info.yaml` dentro de `skeleton/` para que la plantilla registre automáticamente la entidad en el catálogo.
