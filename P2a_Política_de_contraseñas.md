# Política de contraseñas

## Contexto
Por defecto, la mayoría de sistemas operativos, vienen con una política de contraseña muy laxa, una contraseña segura presenta una barrera más al atacante, que en su intento de acceder al sistema, indudablemete dejará más rastro y en algunos casos a provocar el abandondo de ataque.

## Objetivos
* Entender el sistema de contraseñas del sistema operativo linux
* Entender el PAM (Plugable authentication Module)
* Instalar y configurar la libreria _pwquality_
* Comprobar y verificar que se ha llevado la práctica de forma correcta
* Documentar la práctica.

## Sistema de contraseñas Linux
El sistema de contraseñas de linux se divide en 2 archivos:
1. `/etc/passwd`: Este archivo contiene información básica sobre cada usuario del sistema, y cada línea representa a ese usuario y diferentes campos con información de interés, como puede ser su uid o su gid.
2. `/etc/shadow`: Este archivo contiene las contraseñas cifradas e información relevante sobre la cuenta del usuario. Solo puede leerlo el usuario root.

El motivo de la separación en dos archivos, es el aumento de seguridad que supone, ya que a día de hoy todos tienen acceso al archivo passwd, y al separarlo en el archivo shadow que tiene privilegios de usuario aumentamos la seguridad.


## Entender el PAM
PAM actúa como una capa intermediaria entre las aplicaciones y los métodos de autenticación. PAM verifica si un usuario tiene permiso para acceder a un recurso a través de un conjunto de políticas definidas. 

## Instalar y configurar pwquality


|     | Score | Longitud minima | Requisitos | Ejemplos |
|:---:|:-----:|:---------------:|:----------:|:--------:|
|No válida|<35|6|Mínimo 6 caractéres, sin nada más| hola12
|Débil|35-50|6|6 caractéres, dcredit-ucredit = -1| V;n!8s - L@d0s3
|Media|50-80|8|8 caracteres y un numero|T0uriÑlo Bal!3ster
|Extrema|>80|12|12 caracteres, una mayuscula, un numero y un caracteres especial| Cj6`G4Wß;?v0

