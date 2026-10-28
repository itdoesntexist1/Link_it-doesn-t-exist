# ZYOX panel y ofuscación Luau

El Worker de ZYOX puede iniciar el workflow `.github/workflows/prometheus-luau.yml` mediante `repository_dispatch`. El runner descarga temporalmente el archivo desde el Worker, ejecuta Prometheus v0.2.12 con `--LuaU --preset Medium` y devuelve el resultado al Worker. El archivo fuente y la salida no se guardan ni se publican en este repositorio.

El workflow está limitado al archivo de entrada de ZYOX y verifica el SHA-256 del release usado. Para que el Worker pueda iniciar el evento, el propietario debe guardar en Cloudflare el secret `GITHUB_DISPATCH_TOKEN`, creado como fine-grained token para este repositorio con permiso **Contents: Read and write**.

El soporte Luau de Prometheus se describe como básico y aún no completamente terminado; hay que probar el resultado con el script correspondiente.

Based on Prometheus by Elias Oelschner, https://github.com/prometheus-lua/Prometheus
