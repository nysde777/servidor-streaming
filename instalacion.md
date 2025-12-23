1. Actualizar el sistema 
sudo apt update && sudo apt upgrade -y

2. instlar dependencias 
sudo apt install apt-transport-https curl -y

3. agregar al repostiorio oficial 
curl https://repo.jellyfin.org/install-debuntu.sh | sudo bash

---------------------------

Si aparece el error de Insufficient free space for /tmp: 2008104KB found, 2097152KB required
1. Ver el tamaño actual de tmp 
df -h /tmp

2. remontar /tmp con mas tamaño 
sudo mount -o remount,size=4G /tmp

3. reintentar agregar al repositorio oficial 
curl https://repo.jellyfin.org/install-debuntu.sh | sudo bash

-------------------------------------

4. instalar jellyfin 
sudo apt install jellyfin -y

5. Levantar el servicio 
sudo systemctl status jellyfin

6. Si no esta activo activarlo 
sudo systemctl start jellyfin
sudo systemctl enable jellyfin

7. acceder por el navegador 
http://IP_DE_TU_LINUX:8096

8. Estructura recomendada
/media
 ├── Peliculas
 │    └── Interstellar.mkv
 └── Series
      └── Breaking Bad
           └── Season 01.mp4

------------------------------
En el caso de que no reconozca las peliculas 
1. Dar permisos a jellyfin 
sudo chown -R jellyfin:jellyfin /media
sudo chmod -R 755 /media

---------------------------------
9. Ver el hostname actual 
hostname

10. Cambiar el hostname 
sudo hostnamectl set-hostname netflix

sudo systemctl restart systemd-logind

sudo apt install avahi-daemon -y

sudo systemctl status avahi-daemon

http://jellyfin.local:8096
