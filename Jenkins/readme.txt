Ejecutar Jenkins Pipeline

Requisitos
-Tener Jenkins instalado 
-Tener Go instalado
-Tener corriendo las maquinas virtuales lavantadas con Vagrant
-Establecer coneccion ssh con la maquinas virtual "qa"

Para establecer coneccion ssh

- Abrir un terminal y copiar el comando:
     ssh-keygen

- Veras los siguientes mensajes, entonces presiona "enter"
    Generating public/private rsa key pair.
    Enter file in which to save the key (/home/xyz/.ssh/id_rsa):[Press enter key]
    Enter passphrase (empty for no passphrase): [Press enter key]
    Enter same passphrase again: [Pess enter key]

- Ahora copie el siguiente comando: 
    ssh-copy-id -i ~/.ssh/id_rsa.pub vagrant@192.168.33.11

- Pruebe la coneccion ssh con "qa"
    ssh vagrant@192.168.33.11

- Deberia poder conectarse con "qa" sin password

- Por ultimo asegure la coneccion de jenkins a "qa" por ssh
- Copie el archivo "id_rsa" situado en "/home/your_user/.ssh" a "/var/lib/jenkins/.ssh"
- Cree una nueva tarea de tipo pipeline en su jenkins 
- Nombrelo como guste
- Por ultimo copie el archivo JenkinsFile a su pipeline o configurelo para que lo obtenga desde GIT
- Ejecute el pipeline y verifique que el artifact "v1.zip" se haya copiado correctamente a la maquina de "qa"
- Conectese a "qa" y verifique si exite el artifact en el directorio raiz 



