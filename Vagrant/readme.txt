Clonar el repositorio 
#### Para levantar las maquinas virtuales con Vagrant ###

    Pre-requisitos
    -Tener instalado Vagrant 2.2.4
    -Tener instalado virtualbox 6.0

    Pasos 
    - Crear una carpeta Vagrant 
    - Abrir un terminal e ir hasta el directorio donde este su carpeta "Vagrant"
    - Copiar el comando: 
        vagrant init

    - Se debe haber creado un archivo Vagrantfile
    - Reemplace su carpeta "Vagrant" por del repositorio, incluido el archivo Vagrantfile
    - Vaya de nuevo al terminal y ejecute el comando: 
        vagrant up

    - Con esto levantara tres maquinas virtuales, qa, prod y control

 #### Ejecutar ansible playbook ###   

 - Una vez que sus maquinas virtuales hayan levantado
 - Abra un terminal y conectese a "control" por ssh
 - Copie el siguiente comando: 
        vagrant ssh control

 - Eso lo conectara a la maquina virtual "control"
 - Una vez dentro, establesca contacto con "qa" y "prod" via ssh
 - Coloque los siguientes comandos: 

        ssh vagrant@192.168.33.12
        yes
        password: vagrant

    - Con esto se conectara a "prod"
    - Para salir coloque: exit
    - Haga lo mismo para "qa"

        ssh vagrant@192.168.33.11
        yes
        password: vagrant

    - Un vez establecida la coneccion, regrese a "control" con : exit 
    - Dentro de "control" coloque el comando:
         cd /vagrant
         
    - Dentro de la carpeta "Vagrant" esta el archivo "playbook"
    - "Control" debe tener instalado ansible
    - Copie el siguiente comando para ejecutar "playbook.yml" :

        ansible-playbook -i hosts.yml playbook.yml

    - Con esto tendra instalado GIT en las demas maquinas virtuales
    
