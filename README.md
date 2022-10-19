
COMANDOS INFORMACION DEL SISTEMA

arch arquitectura del ordenador
uname -r version del kernel
unane -a sistema operativo, usuario, kernel
cat /proc/cpuinfo informacion sobre la CPU
cat /proc/meminfo verifica uso de la memoria RAM
free -m muestra el estado y uso de la RAM
cat /proc/net/dev adaptadores de red
cat /proc/mounts sistema de archivos montado
COMANDOS NAVEGACION DEL SISTEMA

cd /home/usuario lleva hasta la ruta indicada, ejemplo usuario
cd.. retrocede un nivel de jerarquia de directorios
cd../.. retrocede dos niveles
cd lleva al directorio raiz
cd ~usuario lleva al directorio principal del usuario indicado
cd - lleva al direcotrio anterior
pwd mostrara la ruta del directorio actual
ls muestra los archivos y carpetas
ls -l muestra el detalle de los archivos y carpetas
ls -a muestra los archivos ocultos
CREACION DE DIRECTORIOS

mkdir -p Ejercicio_D/{uba,utnfra}/clase{1..5} crea el directorio
This is an image

tree Ejercicio_D/ ver el directorio

rm -r Ejercicio_D/ borrar de forma recursiva

mkdir -p Ejercicio_E/{utnba/clases{1..5},utnfra/{clases{1..9},examen}}

This is an image

tree Ejercicio_E/
rm -r Ejercicio_E/
CREACION DE ARCHIVOS

cat /proc/cpuinfo > home/1erexamen/CPU.txt
echo -n "Marca=" > cpu.txt && cat /proc/cpuinfo | grep vendor | uniq | cut -d ":" -f2 >> cpu.txt && echo -n "Modelo de CPU=" >> cpu.txt && cat /proc/cpuinfo | grep model | grep name | uniq | cut -d ":" -f2 >> cpu.txt && echo -n "Frecuencia=" >> cpu.txt && cat /proc/cpuinfo | grep MHz | uniq | cut -d ":" -f2 >> cpu.txt && echo -n "Procesadores=" >> cpu.txt && cat /proc/cpuinfo | grep cores | uniq | cut -d ":" -f2 >> cpu.txt
CREACION DE PARTICIONES

sudo fdisk -l Lista todos los discos
sudo fdisk /dev/disco
n
sudo mkfs.ext4 /dev/disco
sudo mount /dev/disco /home/mount
lsblkndos
