# Ejercicio 1

En el primer ejercicio se nos pedia crear una imagen personalizada con alpine:3.20 que instalará curl, crear y copiar un archivo llamado mensaje.txt y definir la instrucción para mostrar el contenido del archivo 
<img width="1107" height="173" alt="ejercicio1_dockerfileMensaje" src="https://github.com/user-attachments/assets/9788b28a-271f-4f07-9f45-a94e543371c0" />
Creación del Dockerfile con la instalación de curl que no viene por predeterminado en alpine.

<img width="998" height="575" alt="ejercicio1_build" src="https://github.com/user-attachments/assets/c0498149-d269-4578-8c4a-c44a1ffaf1ce" />

Se construye la imagen y se ejecuta

<img width="763" height="69" alt="ejercicio1_run" src="https://github.com/user-attachments/assets/926b8521-617d-4f98-8815-3f9620e4d33d" />

Al final se levanta la imagen del docker y se verifica que haya funcionado.

# Ejercicio 2

Se probo la persistencia con volumenes

<img width="974" height="150" alt="ejercicio2_part1" src="https://github.com/user-attachments/assets/9c245d5f-a6d3-4547-8aa9-0f3a174bc0ae" />

Primero se crea el volumen con el nombre especificado. 

<img width="1906" height="71" alt="ejercicio2_part1_2" src="https://github.com/user-attachments/assets/91af31dd-14ea-46d5-a402-73fac8fe7d50" />

Luego se levanta la imagen usando postgres:16-alpine

<img width="1918" height="587" alt="ejercicio2_part2" src="https://github.com/user-attachments/assets/14253eab-86ed-4594-a2d1-db23bd133449" />

Creamos la tabla parcial e insertamos los datos y los mostramos con una consulta.

<img width="832" height="326" alt="ejercicio2_part3" src="https://github.com/user-attachments/assets/c3905b53-ea05-4808-8203-265da80a4596" />

Ahora como se especifico se borro el contenedor y se volvio a levantar uno nuevo usando el mismo volumen.

<img width="828" height="468" alt="ejercicio2_part4" src="https://github.com/user-attachments/assets/88e679b9-64e2-41e9-9fd0-6907e28cc3c6" />

Se verifica que los datos sigan presentes. Comprobando la persistencia.


# Ejercicio 3

Bind mount y edicion en vivo en un index.html

<img width="838" height="221" alt="ejercicio3_part1" src="https://github.com/user-attachments/assets/2427ab35-83d0-4ca8-8999-4fba43527f32" />

Se crea el directorio web y el archivo .html

<img width="842" height="130" alt="ejercicio3_part2" src="https://github.com/user-attachments/assets/9f28aed0-c1ca-4b74-964b-4082fd5c15f4" />

Se ejecuta el contenedor con nginx_alpine

<img width="755" height="168" alt="ejercicio3_part3" src="https://github.com/user-attachments/assets/05b57ed5-23cf-48ec-a7ec-f63184fcdad7" />

Se accede a la dirección especificada del localhost y se verifica

<img width="842" height="151" alt="ejercicio3_part4" src="https://github.com/user-attachments/assets/378218f1-fae4-42d8-b7d5-61ca8a30011a" />

Modificamos el index.html

<img width="1912" height="184" alt="ejercicio3_part5" src="https://github.com/user-attachments/assets/b01e9a36-9fb6-4f68-9fd3-001cb8f7546d" />

Verificamos los cambios simplemente recargando la pagina y se comprueba que funciono

# Ejercicio 4

Se hace exploracion de contenedor

<img width="811" height="154" alt="ejercicio4_part1" src="https://github.com/user-attachments/assets/59db09f1-1475-4095-89b1-b8fd187ed9d6" />

Se ejecuto un contenedor basado en la imagen creada que se ve en el ejercicio 1 con el modo interactivo de /bin/sh

<img width="597" height="200" alt="ejercicio4_part2" src="https://github.com/user-attachments/assets/cff79934-730c-4917-9917-f4687d634d8d" />

Se creo el archivo notas, mostramos directorio y listamos los archivos

<img width="1222" height="267" alt="ejercicio4_part3" src="https://github.com/user-attachments/assets/6ec7b069-01e3-4c50-b3b8-97771912c80a" />

Eliminamos el contenedor y vemos como desaparecio del directorio. Esto es debido a que los contenedores basados en imagenes son efimeros, o sea que cualquier cambio realizado dentro del contenedor se sube pero una vez el ciclo de vida de este contenedor ya no existe, el archivo creado tampoco,su existencia dependía únicamente de la vida del contenedor, y al no haberse guardado en un volumen persistente, se borró junto con el contenedor.


# Ejercicio 5

Se hizo una rpueba de Redis con Dockerfile 

<img width="871" height="208" alt="ejercicio5_part1" src="https://github.com/user-attachments/assets/b346114a-f7a0-48a7-9fc2-726dbef8d892" />

Se contruye el Dockerfile con la imagen base de redis:7

<img width="1393" height="744" alt="ejercicio5_part2" src="https://github.com/user-attachments/assets/2a1ae2d2-9b83-4970-954f-a4754c0ff0d2" />

Se contruyo la imagen con el nombre de nombre-edad

<img width="906" height="77" alt="ejercicio5_part3" src="https://github.com/user-attachments/assets/b1e1f143-addb-487f-8e54-81a416b54b32" />

Se levanto el contenedor en segundo plano usando la flag -d o -detached

<img width="1917" height="522" alt="ejercicio5_part4" src="https://github.com/user-attachments/assets/ca191424-e8e1-4a0f-bf06-0f9e36cdf323" />

Resultado de la salida al verificar si Redis estaba corriendo correctamente...
