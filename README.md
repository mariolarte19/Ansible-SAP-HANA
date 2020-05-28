# Anisble-SAP-HANA 💻

### 1. Información Básicos: 📌
Este playbook configura el sistema Operativo (OS) SUSE SLES for SAP Business Applications 15.0 de acuerdo con las notas SAP aplicables para que se pueda instalar cualquier software SAP. Además Instala SAP HANA EXPRESS 2.0 en un Bare metal con (OS) SUSE SLES.
### 2. Pre-Requisitos 📋
#### 2.1 Requisitos de software.
Compruebe si su sistema tiene el software requerido para instalar y ejecutar con éxito SAP HANA 2.0, edición express
#### A).Sistema operativo :
* SUSE Linux Enterprise Server para aplicaciones SAP, 12.1, 12.2, 12.3 (SPS 02 Rev 23 o superior)
* Java Runtime Environment (JRE) 8 o superior : si planea utilizar el Administrador de descargas de edición expresa de SAP HANA 2.0 para Windows o Linux, necesita el JRE de 64 bits. Si planea usar el Administrador de descargas independiente de la plataforma, puede usar las versiones de 32 o 64 bits. Puede descargar SAP JVM (64 bits) desde https://tools.hana.ondemand.com/#cloud .
#### 2.1 Requisitos de hardware.
Compruebe si su sistema tiene el hardware requerido para instalar y ejecutar con éxito SAP HANA 2.0, edición express.
##### A).CPU soportada:
* Intel 64/AMD64
* IBM POWER 8 (with PowerVM)
* IBM POWER 9 (with PowerVM)

##### B).Disco duro
Para instalar SAP HANA, necesita:
* Disco duro de 120 GB recomendado
##### C).RAM 
El sistema operativo SUSE Linux Enterprise Server requiere un mínimo de 1024 MB de RAM total o un mínimo de 512 MB de RAM por núcleo de CPU (elija el que sea mayor). Cualquier software SAP que instale requerirá RAM adicional. Para instalar SAP HANA, su máquina necesita un mínimo de 16 GB mínimo (se recomiendan 24 GB).
Nota: Si está instalando en un sistema con 16 GB de RAM, aumente la cantidad de espacio de intercambio a al menos 32 GB.
##### D).Nucleos
*	2 núcleos (se recomiendan 4)



### 3. Regístrese en SAP HANA edición express.

##### A).Complete el formulario de registro
Vaya a la página de [registro-Descargar](https://www.sap.com/cmp/td/sap-hana-express-edition.html) y haga clic en Registrarse para obtener su versión gratuita.
##### B).Elige un administrador de descargas.
Haga clic en el administrador de descargas que coincida con su sistema: Linux DM o Windows DM.
##### C).Elige un administrador de descargas.
Guarde el archivo del administrador de descargas en su computadora portátil y ábralo. Si su sistema muestra una advertencia de seguridad cuando abre el archivo, ignore la advertencia.
### 3.Descripción de Tareas Playbook 🚀

#### 3.1 Crea directorio.
Se crea un directorio en /home/saphana , con el fin de alojar el instalador de SAP HANA EXPRESS 2.0.
#### 3.2 Instalar grupo de paquetes sap-hana.
En esta tarea se instala paquetes tales como: 
* sysstat para recopilar datos sar.
* tuned para el ajuste del sistema.
* uuidd proporciona identificadores únicos universales, esenciales para crear claves de base de datos.
#### 3.3 Instalar una lista de paquetes adicionales.
* java,libatomic1,nfs-utils,tcsh,psmisc y glibc

#### 3.4 solución saptune aplicar HANA
Utilizando saptune, se puede ajustar el sistema para SAP NetWeaver, SAP HANA / SAP Business Objects y aplicaciones SAP S / 4HANA.
En esta tarea se configurar saptune con una solución preconfigurada la cual es HANA .

 * 2382421: Optimizar Configuración de red a nivel HANA y OS.
            Version 36 from 16.01.2020
 * 2534844: Bloqueo del Indexserver durante el inicio debido a un segmento de memoria compartida insuficiente.
            Version 12 from 15.11.2017
 * 2578899: SUSE LINUX Enterprise Server 15: Notas de instalación.
            Version 20 from 29.11.2019
 * 2684254: SAP HANA DB: Configuración recomendada del sistema operativo para SLES 15 / SLES para aplicaciones SAP.
            Version 5 from 03.01.2019
 * 941735: Sistema de gestión de memoria SAP para sistemas Linux de 64 bits.
           Version 11 from 04.05.2018
 * 1980196:Configuración del parámetro del núcleo de Linux /proc/sys/vm/max_map_count en SAP HANA Systems.
 * 1771258: Linux: Límites de recursos de usuario y sistema.
            Version 5 from 18.06.2018


#### 3.5 saptune daemon start
#### 3.6 Gestor de descargas
#### 3.7 Descargar instalador de sap hana
#### 3.8 Descomprimir instalador
#### 3.9 Procesar la plantilla de archivo de configuración de HANA"	
#### 3.10 Instalar SAP HANA

##  Construido con 🛠️
IBM Cloud, Ansible.



## Wiki 📖
Para más información [Watson-Visual Recognition](https://www.ibm.com/co-es/cloud/watson-visual-recognition)


## Autores ✒️
Team IBM Cloud



