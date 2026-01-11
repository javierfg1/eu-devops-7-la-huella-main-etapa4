#### Todo tiene sentido cuando se despliega


Sala de café de La Huella. Miércoles. 08:30h.


Lía hojea su cuaderno, Álex bosteza sin disimulo y Kel se ríe contando cómo el terraform state list de Marcos parecía la lista de la compra más técnica del mundo.

—La cara de concentración que puso ayer cuando lo consiguió… —dice Álex, imitando la pose—. Puro “DevOps zen”.


Marcos se ríe.

—Yo aún estoy flipando con la cantidad de recursos que declaró. Terraform me da respeto —añade Lía.


Kel asiente con gesto teatral.

—Marcos, oficialmente IaC master.


Ríen todos.


Justo en ese momento entra Iñaki, con paso rápido y sonrisa madrugadora.

—Buenos días, equipo. Marcos, hoy el reto es corto. No vas a tener que filosofar mucho ni reescribir el mundo. Es solo desplegar la app y dejarla hablando con lo que montaste.


Hace una pausa, guiño incluido:

—Tienes todo en el email, no te robo más tiempo. Tengo prisa.


Se va dejando tras de sí el rumor de las carcajadas.


Marcos, curioso, regresa a su mesa y abre el portátil.


> Email:

Asunto: Cierra el círculo: despliega la app
De: Iñaki Lorenzo (ilorenzo@lahuella.com)
Para: Marcos Varela


¡Hola, Marcos!


Lo que toca ahora es sencillo: desplegar la aplicación sobre la infraestructura que ya creaste con Terraform en Localstack.


Pasos clave:

Usa el repositorio de la aplicación (https://github.com/missions-labs/eu-devops-7-la-huella). Recuerda que es necesario que clones el repositorio y lo subas a tu cuenta de GitHub.

Asegúrate de que todo apunta correctamente a tu infraestructura (endpoint Localstack incluido).

Ejecuta el script script/init.sh para poblar datos en los recursos (ojo: si el endpoint de Localstack ha cambiado, ajusta antes de lanzar).

Finalmente, despliega la aplicación en tu local y comprueba que todo funciona correctamente.


Hoy no hay trampas ni curva extra: es dejar que todo fluya y comprobar que lo que levantaste cobra vida con la app.


Hazlo con el mismo detalle de siempre, pero tranquilo.


Abrazo,
Iñaki


Marcos sonríe aliviado, coge su bloc y apunta rápido:

Ajustar endpoints en config.

Ejecutar script/init.sh.

Verificar datos poblados.


Con esa claridad abre Slack:


> Chat de equipo (Slack):

Marcos:​​ Chicos, próxima etapa en marcha. Ahora me toca desplegar la app en la infra creada y correr init.sh para poblar datos. Parece directo.
Álex: Perfecto. Dale con calma, ya lo tienes en bandeja.
Lía: Vaya sensación cerrar el círculo, ¿eh?
Kel: Este es de los que se disfrutan: menos comandos raros, más ver todo vivo. 🚀
Iñaki: Eso es. Disfrútalo, Marcos. Con tu detalle, lo vas a cerrar con nota.


Marcos se frota las manos, motivado. Abre el repo y susurra para sí:

—Hora de ver la app cobrar vida.


Recuerda que tienes las instrucciones detalladas de las tareas justo aquí debajo 😉


Instrucciones

Usa el repositorio de la aplicación (https://github.com/missions-labs/eu-devops-7-la-huella). Recuerda que es necesario que clones el repositorio y lo subas a tu cuenta de GitHub.

Asegúrate de que todo apunta correctamente a tu infraestructura (endpoint Localstack incluido).

Ejecuta el script script/init.sh para poblar datos en los recursos (ojo: si el endpoint de Localstack ha cambiado, ajusta antes de lanzar).

Finalmente, despliega la aplicación en tu local y comprueba que todo funciona correctamente.


La evaluación:

Sube un PDF con evidencias de que los recursos que has creado en Localstack a través de Terraform han sido poblados con el script init.sh y de que la aplicación desplegada puede acceder a los mismos correctamente.


