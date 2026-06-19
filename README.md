# Pipeline CI/CD con GitHub Actions y Docker

## Objetivo

Implementar un pipeline CI/CD que valide una aplicacion Bash, construya una imagen Docker y ejecute el flujo automaticamente con GitHub Actions en cada `push`.

## Archivos del proyecto

- `app.sh`: aplicacion base que ejecuta el pipeline.
- `Dockerfile`: definicion de la imagen Docker.
- `.github/workflows/pipeline.yml`: workflow de GitHub Actions.

## Comandos iniciales

```bash
chmod +x app.sh
git add .
git commit -m "pipeline completo"
git push
```

## Simular error

Modificar `app.sh` con este contenido:

```bash
#!/bin/bash
echo "Error intencional"
exit 1
```

Subir el error:

```bash
git add .
git commit -m "error para probar pipeline"
git push
```

El pipeline debe fallar porque el script termina con `exit 1`.

## Corregir error

Modificar `app.sh` con este contenido:

```bash
#!/bin/bash
echo "Error intencional"
exit 0
```

Subir la correccion:

```bash
git add .
git commit -m "corregir error del pipeline"
git push
```

El pipeline debe volver a funcionar porque el script termina con `exit 0`.

## Relacion con DevOps

- CI: ejecuta validaciones automaticamente.
- CD: construye la imagen Docker como artefacto.
- Docker: empaqueta la aplicacion.
- Cloud: GitHub Actions ejecuta el pipeline en la nube.
