# it-projects
Mi laboratorio personal de sistemas, redes y automatización.


 Hito 1: Despliegue de Servidor Base (servidor-lab-01)
- Sistema Operativo: Ubuntu Server LTS
- Virtualización: VirtualBox
- Configuración de Disco: Particionado automático con soporte LVM (Logical Volume Manager).
- Servicios iniciales: Servidor OpenSSH instalado y configurado para acceso remoto.

<img width="512" height="489" alt="lab01" src="https://github.com/user-attachments/assets/b607d9b5-313a-4592-aed5-da5c8e1353fb" />

---------------------------------------------------------------------------------------------------------------------


Hito 2: Configuración de red y primer acceso SSH remoto
- Red: Adaptador Puente configurado en VirtualBox para integración en la red local (192.168.1.128).
- Gestión: Conexión segura por SSH desde la terminal de Windows (PowerShell) hacia el servidor virtual (servidor-lab-01).
- Estado: Servicio OpenSSH verificado y operativo para administración desatendida.
  
<img width="1092" height="629" alt="primerssh" src="https://github.com/user-attachments/assets/0a09c302-7b6c-4570-93f4-c266731df84a" />

------------------------------------------------------------------------------------------------------------------------


Hito 3: Seguridad y Endurecimiento con UFW

-En este hito se ha implementado una capa de seguridad perimetral en servidor-lab-01 utilizando UFW (Uncomplicated Firewall) para proteger el sistema frente a accesos no autorizados.

-Verificación del estado inicial: Comprobación de que el cortafuegos venía inactivo por defecto.

-Apertura del puerto SSH: Configuración preventiva para permitir el puerto 22/tcp antes de activar el bloqueo total, evitando así la desconexión de la sesión en PowerShell.

-Activación de UFW: Habilitación del cortafuegos para que arranque con el sistema aplicando una política estricta de denegación de tráfico entrante.

-Comprobación final: Verificación mediante sudo ufw status verbose confirmando la política deny (incoming) y las reglas activas para SSH.

<img width="804" height="633" alt="cortafuegos" src="https://github.com/user-attachments/assets/bdb95872-bbc3-4ae8-8eb3-692bc88fe6ba" />


----------------------------------------------------------------------------------------------------------------------

Hito 4: Despliegue de un Servidor Web (Nginx) y Gestión de Servicios

- Objetivo: Desplegar un servidor web Nginx en Ubuntu Server para aprender a gestionar paquetes del sistema (`apt`), controlar servicios (`systemctl`), configurar reglas en el cortafuegos (UFW) y verificar el acceso visual desde el equipo anfitrión mediante una red en puente.
- Proceso y Comandos Ejecutados
Se actualizó la lista de paquetes del sistema, se instaló Nginx mediante el gestor de paquetes oficial, se comprobó el estado de actividad del servicio (saliendo del paginador con la tecla `q`), se abrió el puerto 80 en el cortafuegos y se confirmó la visualización de la página de bienvenida en el navegador.

bash
sudo apt update (actualizar los paquetes)
sudo apt install nginx -y (instalar nginx)
sudo systemctl status nginx 

<img width="944" height="704" alt="1c616dc7-2229-433e-ae5d-4f72c3cd7975" src="https://github.com/user-attachments/assets/48b8ede9-0c28-49d8-9e28-0de03942a688" />

sudo ufw allow 80/tcp 

<img width="948" height="317" alt="c4d9e678-54e1-4196-ba57-d38a14c42ff3" src="https://github.com/user-attachments/assets/2a99cee1-0efe-4968-9875-19cd9d7f83c9" />
