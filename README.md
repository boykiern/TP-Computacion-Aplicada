# Trabajo Práctico Integrador - Computación Aplicada

## Alumno

- Nicolas Boykier
  
## Descripción

El repositorio tiene:
- root.tar.gz (Backup del directorio /root).
- etc.tar.gz (Backup del directorio /etc, donde estan configuraciones del sistema como red, SSH, fstab y servicios).
- opt.tar.gz (Backup del directorio /opt, tiene el archivo /opt/particion y el script /opt/scripts/backup_full.sh).
- www_dir.tar.gz (ackup del directorio /www_dir montado sobre la partición de 3gigas).
- backup_dir.tar.gz (Backup del directorio /backup_dir montado sobre la partición de 6gigas).
- El directorio /var lo comprimi y dividi en partes de 20MB para poder subirlo al repostiorio (Va desde var.tar.gz.part_aa hasta var.tar.gz.part_an).

## Resumen de lo que se hizo:
- Importe la maquina virtual desde VirtualBox.
- Configure el acceso a root (el super usuario).
- Cambie el hostname a TPServer.
- Actualice el SO a DEbian 12.
- Configure SSH para acceso root con clave publica.
- Instale APache, PHP y MariaDB como figuraba en el anuncio del curso.
- Importe la base de datos desde db.sql.
- Configure la interfaz "enp0s3" con IP estatica.
- Agregue un disco virtual adicional de 10gigas.
- Lo particione en 2:
    - /dev/sdc1 de 3 gigas montada en /www_dir.
    - /dev/sdc2 de 6 gigas montada en /backup_dir.
- Configure el montaje automatico en /etc/fstab.
- Cree el archivo /opt/particion con el contenido de /proc/partitions.
- Cree el script /opt/scripts/backup_full.sh.
- Configure tareas automatizas con cron.

## Configuracion de red
- La interfaz principal es la placa de red de la máquina virtual. En mi caso se llamaba enp0s3 (lo vi con ip a). Le puse una IP, mascara de red y gateway.

## Script de backup
- El script (que se encuentra en /opt/scripts/backup_full.sh) permite hacer backups poniendo origen y destino.

## Tares programados con cron
- Configure para realizar un backup diario de /var/log a las 00 y tambien que se haga backup de www_dir los lunes, miercoles y viernes a las 23.

## Conclusion
Al final la maquina virtual quedo configurada con debian 12, red estatica, acceso SSH, servidor web con PHP, base de deatos MariaDB, particiones adicionales montadas automaticamente y sistema de backup automatico como pedia la consigna.
