# Trabajo Práctico Integrador

## Participantes

- Miguel Nicolás Cáceres Yrala  
- Tadeo Lomas

## Descripción del trabajo

Este proyecto corresponde al Trabajo Práctico Integrador de la materia **Administración de Servidores**.  
El objetivo fue realizar una instalación, configuración y despliegue funcional de un servidor Linux Debian con múltiples servicios.

## Contenido y pasos realizados

### 🔧 Configuración del servidor
- Se usó una máquina virtual con Debian 11.
- Se creó un sitio web funcional utilizando **Apache2**, alojado en `/mnt/www_dir`.
- Se copiaron los archivos `index.php` y `logo.png` al sitio, ajustando permisos (`chmod`) y propietarios (`chown`) al usuario `www-data`.

### 🔐 Seguridad y conexión remota
- Se configuró el servicio **SSH** para permitir el acceso con clave pública.
- Se generó una clave SSH con `ssh-keygen` y se agregó correctamente a GitHub para hacer **push con autenticación SSH**.

### 🛠️ Automatización de tareas
- Se creó un script de backup (`backup.sh`) que guarda registros desde `/var/log` y `/mnt/discoextra`.
- Se configuró un archivo `crontab.txt` con múltiples tareas programadas, incluyendo el backup automático, copias de logs y compresión.

### 💾 Manejo de base de datos
- Se exportó un archivo `db.sql` simulando una base de datos para la parte web.

### 📁 Administración de archivos grandes
- Se intentó subir todo a GitHub, pero se detectó que el archivo `www_disk.img` excedía el límite de 100MB.
- Para resolverlo:
  - Se eliminó el archivo del control de versiones con `git rm --cached`
  - Se creó el archivo `.gitignore` para excluirlo del repo
  - Se utilizó `git filter-branch` para purgar el historial del archivo pesado.

### ☁️ Subida a GitHub
- Se configuró correctamente el repositorio Git, se realizó el commit inicial y se subieron todos los archivos por SSH.
- El proyecto quedó alojado en: [github.com/miguelcaceres-alt/Trabajo-Practico](https://github.com/miguelcaceres-alt/Trabajo-Practico)

---

## Archivos importantes

- `index.php` → Página web de prueba
- `logo.png` → Imagen del sitio
- `backup.sh` → Script de backup
- `crontab.txt` → Tareas programadas
- `db.sql` → Exportación de base de datos
- `particion`, `proc.tgz` → Respaldos del sistema
- `.gitignore` → Exclusión de archivos pesados como `www_disk.img`

---

## Estado

✅ Proyecto finalizado y funcional  
🗓️ Fecha de entrega: Junio 2025
