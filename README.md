# it-projects
Mi laboratorio personal de sistemas, redes y automatización.


 Hito 1: Despliegue de Servidor Base (servidor-lab-01)
- Sistema Operativo: Ubuntu Server LTS
- Virtualización: VirtualBox
- Configuración de Disco: Particionado automático con soporte LVM (Logical Volume Manager).
- Servicios iniciales: Servidor OpenSSH instalado y configurado para acceso remoto.

<img width="512" height="489" alt="lab01" src="https://github.com/user-attachments/assets/b607d9b5-313a-4592-aed5-da5c8e1353fb" />


Hito 2: Configuración de red y primer acceso SSH remoto
- Red: Adaptador Puente configurado en VirtualBox para integración en la red local (192.168.1.128).
- Gestión: Conexión segura por SSH desde la terminal de Windows (PowerShell) hacia el servidor virtual (servidor-lab-01).
- Estado: Servicio OpenSSH verificado y operativo para administración desatendida.
- 
<img width="1092" height="629" alt="primerssh" src="https://github.com/user-attachments/assets/0a09c302-7b6c-4570-93f4-c266731df84a" />


Hito 3: Seguridad y Endurecimiento con UFW
-En este hito se ha implementado una capa de seguridad perimetral en servidor-lab-01 utilizando UFW (Uncomplicated Firewall) para proteger el sistema frente a accesos no autorizados.
-Verificación del estado inicial: Comprobación de que el cortafuegos venía inactivo por defecto.
-Apertura del puerto SSH: Configuración preventiva para permitir el puerto 22/tcp antes de activar el bloqueo total, evitando así la desconexión de la sesión en PowerShell.
-Activación de UFW: Habilitación del cortafuegos para que arranque con el sistema aplicando una política estricta de denegación de tráfico entrante.
-Comprobación final: Verificación mediante sudo ufw status verbose confirmando la política deny (incoming) y las reglas activas para SSH.

<img width="804" height="633" alt="cortafuegos" src="https://github.com/user-attachments/assets/bdb95872-bbc3-4ae8-8eb3-692bc88fe6ba" />
