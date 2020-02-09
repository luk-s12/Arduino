# Arduino

## Instalación en arch linux

### Actualizamos la maquinola primero
```bash
  sudo pacman -Syuu
```
### Despues instalamos los paquetes arduino 

```bash
  sudo pacman -S arduino arduino-docs arduino-avr-core
```
### Despues de la instalación 

Debemos dar permisos al usuario al los siguientes **grupos**: 
  - uucp
  - lock
  
```bash
sudo gpasswd -a NOMBRE_DEL_USUARIO uucp
sudo gpasswd -a NOMBRE_DEL_USUARIO lock
```

> Nota: Para obtener el nombre usuario podemos usar el comando **whoami**  en el terminal 

Despues debemos **conectar la arduino a la maquinola** y fijarse que **puerto** esta usando para poder dar **permisos
al usuario**.

**Una vez conectada la aurduino** ejecutamos los siguientes comandos:

```bash
sudo ls -l /dev/ttyACM*
```
Si al ejecutar el anterior comando  no hay una respuesta valida que encontro el puerto debemos ejecutar el siguiente comando

```bash
sudo ls -l /dev/ttyUSB*
```
Dependiendo cual de los 2 anteriores comandos de una respuesta valida. Debemos dar permiso al puerto que esta usando
la arduino. En mi caso esta usando el **ttyACM0**

```bash
sudo chmod 777 /dev/ttyACM0
```
Listo ya quedo todo para probar la arduino. Simplemente hay q entrar al ide de arduino y seleccionar el tipo de arduino y puerto que se usa en la pestaña de **herramientas**



