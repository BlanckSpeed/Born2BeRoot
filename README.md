# Born 2 Be Root

• Entregar archivo signature.txt en la raiz del repo<br>
• Pegar firma del disco virtual de la maquina.

1. Instalar servidor con el mínimo de servicios
2. Elegir version estable entre Debian o Rocky.
3. En Rocky configurar Kdump.
4. SELinux debe ejecutarse al iniciar, con configuraciones adaptadas al proyecto.

Linux con seguridad mejorada, es un sistema de control obligatorio de acceso basado en la interfaz LSM (es un framework that allows Linux kernel support without bias a variety of computer security models) En la práctica, el núcleo pregunta a SELinux antes de cada llamada al sistema para saber si un proceso está autorizado a realizar dicha operación.
SELinux utiliza una serie de reglas - conocidas en conjunto como una política para autorizar o denegar operaciones. 
Se proporcionan dos políticas estándar (targeted, dirigida, y strict, estricta) 


AppArmor es un sistema de control obligatorio de acceso (MAC) basado en la interfaz LSM (es un framework that allows Linux kernel support without bias a variety of computer security models) En la práctica,  el núcleo pregunta a AppArmor antes de cada llamada del sistema para saber si un proceso está autorizado a realizar dicha operación. AppArmmor confina un programa a un conjunto limitado de recursos. 


5. AppArmor en Debian debe ejecutarse al iniciar. 
6. Crear al menos 2 particiones cifradas usando LVM.
7. Estudiar sistema operatio, diferencias entre aptitude y apt, o que son SELinux y AppArmor. 
8. Puerto SSH ejecutara en el puerto 4242
9. No debe ser posible conectarse a traves de SSH como root
10. Entender el uso de SSH
11. Configurar S.O con el firewall UFW(o firewalld en Rocky) dejando el puerto 4242 abierto en la VM.
12. Firewall debe estar activo cuando se ejecute la VM (firewalld para Rocky).
13.  hostname = rlendine42 (modificar hostname durante evaluacion)
14. Implementar política de contraseñas fuerte.
15. Instalar y configurar sudo siguiendo las reglas estrictas.
16. un usuario con nombre de rlendine a parte del usuario root
17. rlendine debe pertenecer a los grupos user42 y sudo
18. Saber crear usuarios y asignarlo a un grupo
19. Configurar política de contraseñas fuerte con: 
• expira cada 30 días, número mínimo de días permitido antes de modificar una contraseña son 2
• Usuario recibe mensaje de aviso 7 días antes de que la contraseña expire.
• Contraseña con 10 caracteres mínimos. Contener una mayúscula y un número. No tener más de 3 veces consecutivas el mismo carácter.
• Contraseña no puede ser nombre de usuario
• rlendine: contraseña debe tener 7 caracteres que no sean de antigua contraseña
• root debe seguir esta política
• después de preparar los archivos de configuración, cambiar contraseña de todas cuentas.
20. Contraseña fuerte para grupo sudo:
• Autenticarse con sudo debe estar limite 3 intentos, en el caso de introducir una contraseña incorrecta
• Mensaje personalizado de tu eleccion, en caso de que la contraseña introducida sea incorrecta y se utilice sudo
• Comando ejecutado con sudo, tanto el input como el output deben quedar archivados en el directorio /var/log/sudo/
• El modo TTY debe estar activado por razones de seguridad
• Directorios utilizables por sudo deben estar restringidos. Ejemplo: /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/sbin:/snap/bin
21. Crear script llamado monitoring.sh desarollado en bash.
22. Cuando el servidor inicie, script mostrará cierta información (listada debajo) en todos los terminales cada 10 minutos (buscar wall) banner de wall opcional. Ningún error debe ser visible.
23. Tu script debe siempre mostrar:
• Arquitectura de tu sistema operativo y su version kernel
• Número de núcleos físicos.
• Número de núcleos virtuales.
• Memoria RAM disponible actualmente en tu servidor y su porcentaje de uso.
• Memoria disponible actualmente en el servidor y utilizacion como porcentaje
• Porcentaje actual de uso de núcleos.
• Fecha y hora del último reinicio.
• Si LVM  esta activo o no.
• El número de conexiones activas.
• El número de usuarios del servidor.
• La dirección IPv4 de tu sistema servidor y su MAC (Media Access Control).
• Número de comandos ejecutados con sudo.
• Buscar cron para responder como funciona el script
• Revisar imagenes de subject


