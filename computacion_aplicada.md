# Computación aplicada
Profesor: Matias Chiesa - Online Asincrónica

Fecha de final: Miércoles 10/07/2024 de 18:00hs a 21:00hs 

## Trabajo práctico
#### SSH
* Se revisan los dispositivos de red, para saber cual es el nombre en el OS con el comando `ip address`. Esto muestra la lista de dispositivos de red, y su direccion MAC. 
* Se instala el paquete de ssh con `apt install openssh-server`
* Para conectarse a `caservidor` desde mac, por la terminal se ejecuta `ssh caservidor@192.168.64.3` y se usa la contraseña de `caservidor`
#### DHCP

#### Montaje de disco
* Desde UTM (es lo que yo usaba) agrego un disco nuevo IDE.
* Con `sudo fdisk -l` o `lsblk` listo los dispositivos de bloque.
  * En este caso, veo que esta `sdc` como dispositivo (es el que agregué).
* Con `sudo fdisk /dev/sdc` elijo las opciones:
  * `n` para hacer una particion nueva, que elegiré primaria, con las demás opciones por defecto.
  * `w` para escribir los cambios
* Con `sudo fdisk -l` o `lsblk` listo los dispositivos de bloque.
  * Veo que está `sdc/sdc1`
* Con `sudo mkfs -t ext4 /dev/sdc1` creo el filesystem
* Creo un directorio en `/media` para montar el disco, llamado `testsdc` 
* Con el comando `sudo blkid` consigo el UUID, que es el identificador unico para el dispositivo.
* Edito el archivo `/etc/fstab`, con la siguiente linea para que se monte automaticamente `UUID=uuid_de_sdc /media/sdc1 ext4 defaults 0 2`.
  * Para que el sistema lo detecte, se reinicia o se ejecuta `sudo mount -a && sudo systemctl daemon-reload`
  * Y por ultimo, para confirmar que el disco este montado (y su punto de montaje), se ejecuta: `df -hT`
#### Backup
#### Crontab

## FHS
## Comandos
## Instalación
## Pipes y redirecciones
## Editores
## Usuarios y permisos
## Discos y links
## Procesos y alias
## Inicio
## Redes y SSH
## Scripts y cronjobs