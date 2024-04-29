# robot

## Instalacion Ubuntu 20.04 

Descargar e instalar Ubuntu 20.04 Desktop en Raspberry Pi

- Descargar Ubuntu 20.04 Desktop
https://releases.ubuntu.com/focal/ o descargar en la carpeta

- Descargar Raspberry Pi Imager
https://www.raspberrypi.com/software/

- Ejecutar archivo ejecutable de Raspberry Pi Imager (imager_1.8.5.exe)

- Abrir Raspberry Pi Imager e instalar ubuntu el memory card

## Configurar Ubuntu 

- Cambiar el idioma del sistema por Español y reiniciar
- Cambiar de nuevo el idioma del sistema por Ingles y reinciar
- Ver este video y seguir los pasos

## Configurar conexion inalambrica

- Escribir en terminal
  ip addr

- Buscar la direccion IP relacionada a wlan0 y copiar la direccion
  ![image](https://github.com/sValderas1997/robot/assets/135936397/1b5de343-28bd-43b8-b6ce-25efc9c84bed)

- Crear archivo en la carpteta netplan
  sudo pluma /etc/netplan/02-my-network-config.yaml
- En el raspberry pi se necesita tener el archivo ...pi.yaml mientras que en el computador base se necesita tener dev.yaml 
  ![image](https://github.com/sValderas1997/robot/assets/135936397/8d1cb4d8-c959-47e4-8818-d030a99153cc)
- Para aplicar los cambios ejecutar
  sudo netplan generate
  sudo netplan apply
- Eliminar la red anterior en configuracion de red avanzada
- Instalar en raspberry ssh
  sudo apt install openssh-server
## Instalar ROS 2
-Instalar paquetes
  sudo apt update
  sudo apt install curl gnupg2 lsb-release
  sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg
  echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null
  sudo apt update
  sudo apt install ros-foxy-desktop python3-argcomplete
- Comprobar si funciono
  source /opt/ros/foxy/setup.bash
  ros2 run demo_nodes_cpp talker
- Instalar Colcon
  sudo apt install python3-colcon-common-extensions
  echo "source /opt/ros/foxy/setup.bash" >> ~/.bashrc

