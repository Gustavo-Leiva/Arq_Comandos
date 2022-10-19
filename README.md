
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

sudo du -sh /etc/ para ver el tamaño de etc
sudo du -sh /home/ para ver el tamaño de home


istorial de comando
c = nos permite movernos a distintos directorios
- = representa un archivo
. = (no lo se, me perdi xd)
pwd = donde estoy parada
/proc = directorio se ccrea en memoria contiene la misma informacion de proceso de lo que ejecuto, le da este numero para  para identificarlo 
cat= puedo ver contenido de archivos
cat meminfo = da informacion de memoriam(total, libre,etc)
cat /etc/passwd = 
cd /tmp = d
cd /- = para ir al directorio anterior
more /etc/passwd (ctrl r) = busqueda recursida sobre historial de comandos. Sirve para buscar un comando usado anteriormente. 
ctrl + flecha derecha/izq = salta palabra por palabra
ctrl + w = borra una palabra
/root = se paro el sist en algun lugar donde existia esta palabra
cat o less o more = hacen lo mismo
ctrl +e = para ir al final del comando
cp = permite hacer copias
cd = sirve para ir a nuestro propio home, donde nos logueamos
whoami = para saber cual es nuestro nombre de usuario
cp (directorio que quero)/etc/host .(. = donde estoy parada) = sirve para copiar un archivo
cd -> change dir
pwd -> muestra donde estas parada
cat,less, more -> mostrar contenido de un archivo
whoami  -> saber que usuario soy
cp -v /etc/hosts /tmp = (-v) = ejecuta comando en modo debug, mayor nivel de debug mientras mas v se le agregan
man - k = apropos copy
apropos copy = muestra los comandos que se pueden usar para copiar
man -k network = muestra comandos relacionados a red (network) creo... xd
mandb = actualiza la base de datos
cp -a /etc . = copia los archivos (la carpeta, manteniendo permisos pero no los dueños) de manera recursiva a donde estoy parado
ls  -l /etc/h* = el asterisco es para que te liste los archivos que empiezan con h; reemplaza el resto de la palabra
mv = mueve o renombra archivos
echo = muestra algo por pantalla 
cut << (palanra q yo quiera) FIN = puedo escribir multiples lineas hasta escribit la palabra que  elegi = FIN
cat << FIN > salida.txt = igual que el anterioir, pero la salida se redirecciona a un archivo de texto
cat << FIN >> salida.txt = doble piquito mayor de redireeccon agregar contenido al archivo al final
ls -r/etc/t*  =>lista en orden inverso
ls -l /etc/[^t]* => ignoro la archivos que empiecen con t
pwd =>donde estoy parada
mkdir -p /home/maia/Pandemia/pandemita => crea directorio dentro de otro directorio (dentro de pandemia)
rmdir NOMBRE => borra directorio
rm -rf NombreDirectorio/* => elimina el contenido de directorio
whoami => ver nombre de usuario
free -m => ver informacion de disponibilidad y consumo de ram
more => ver consumo de ram 
grep model name /proc/cpuinfo =>filtrar para ver solo nombre de cpu
/proc/cpuinfo => ver modelo de cpu
sudo du -sh /nombreDirectorio/ => saber cuanto pesan directorio 
mkfs.ext4 /dev/NombreParticion => formatear
mount /dev/partición /carpetaDestino => montar
lsb_release => información distribución
cat /etc/issue => nombre distribución
dmidecode -q => componentes (hardware) de sistema
hdparm -i => /dev/hda =>características disco duro
hdparm -tT /dev/sda prueba lectura disco duro
cat /proc/cpuinfo => información de la cpu
grep -c ^processor /proc/cpuinfo => número de procesadores
cat /proc/interrupts => mostrar interrupciones
cat /proc/meminfo => verificar uso de memoria 
cat /proc/swaps =>mostrar ficheros swap
cat /proc/version => mostrar version de kernel
cat /proc/net/dev=> mostrar adaptadores de red y estadísticas
cat /proc/mounts => sistema de ficheros montado
lscpu => mostrar info sobre microprocesador
lspci -tv =>mostrar dispositivos PCI
lsusb -tv =>  mostrar dispositivos USB
lshw => listar hardware
cat /proc/meminfo => ver uso de memoria ram
date => muestra fecha actual



cat /proc/cpuinfo | grep vendor | uniq | cut -d ":" -f2 >> cpu.txt
-el cat me trae el contenido de /proc/cpuinfo
-el pipe separa las acciones
-el grep filtra y me trae solo las lineas que contengan la expresion 'vendor'
-el uniq elimina los resultados repetidos (importante xq el cpuinfo tiene la misma info duplicada - por eso aclaran en el ejercicio que solo aparezca una vez)
-el cut le pido que a toda esa línea la separe con un delimitador (-d) en este caso ":"
- ahora la linea me quedó delimitada en 2 por el ":" entonces con el -f (--field) le indico cual de esas dos partes quiero (-f1 anterior | -f2 posterior)
-y finalmente eso lo guardo haciendo una append al archivo ya existente
>> cpu.txt

