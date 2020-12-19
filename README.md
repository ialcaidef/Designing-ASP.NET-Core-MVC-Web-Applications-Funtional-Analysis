# Designing-ASP.NET-Core-MVC-Web-Applications-Funtional-Analysis
MOD02_LAK_FUNCTIONAL_ANALYSIS

# Aplicación web para compartir fotos de Adventure Works (propuesta)

## Introducción

La junta de Adventure Works ha pedido a los Autores que investiguen la posibilidad de crear una aplicación web pública para compartir fotos, en la que los clientes de Adventure Works puedan compartir fotografías de las atracciones, bicicletas, otros equipos y cualquier otra imagen. Los objetivos de este sitio son crear una comunidad de usuarios de equipos de Adventure Works y alentar a los clientes a participar para compartir sus experiencias.

Hemos entrevistado a miembros de la junta, clientes, administradores de aplicaciones web y otras partes interesadas y presentamos en este documento una propuesta para una aplicación web adecuada y su amplia funcionalidad. Hemos incluido:

•	Una descripción general de la aplicación web propuesta y su funcionalidad prevista.   
•	Una serie de casos de uso que describen tareas que los clientes pueden completar en la aplicación web para compartir fotos.   
•	Transcripciones de entrevistas a clientes.   
•	Algunas recomendaciones técnicas.   

Los *Autores* esperan que este documento defina claramente el alcance de la aplicación web, permita a los miembros de la junta aprobar el desarrollo del proyecto y proporcione toda la información que los desarrolladores necesitan para comenzar su trabajo.

*Nota:* Este documento no pretende ser una descripción final de la aplicación web que se creará. A medida que avanza el proyecto, se pueden agregar funciones adicionales y se pueden perfeccionar las especificaciones que se dan en este documento. Estos cambios deben realizarse en consulta con las partes interesadas. Los directores de proyecto deben tomar las decisiones finales sobre tales adiciones y mejoras.

## Descripción general de la aplicación web para compartir fotos

La aplicación web propuesta para compartir fotos debe permitir a los usuarios cargar, compartir y discutir fotografías. Los usuarios deben poder:

•	Subir una foto que hayan tomado. Las fotos deben tener un formato de imagen común, pero generalmente serán JPEG.   
•	Agregue a sus fotos títulos, descripciones y otros metadatos.   
•	Eliminar fotos.   
•	Ver fotos individuales en tamaño grande.   
•	Agregar comentarios a las fotos.   
•	Examinar todas las fotos del sitio.   

La aplicación web debe estar disponible para que cualquier visitante explore las fotos sin iniciar sesión. Esto puede actuar como una oportunidad publicitaria para el equipo de Adventure Works porque aquellos sin credenciales para el sitio pueden ver las bicicletas en acción y una comunidad de usuarios vibrante. Sin embargo, los usuarios anónimos no deben poder realizar cambios en las fotos o agregar comentarios en el sitio: esto requiere una cuenta de usuario.
Aunque la aplicación web para compartir fotos no se considera fundamental para Adventure Works, se debe requerir un cierto nivel de resistencia a fallas del servidor y otros desastres por las siguientes razones:

•	Si el sitio para compartir fotos no está disponible, los clientes pueden comprar productos en el sitio de Internet principal de Adventure Works. La participación del cliente es el objetivo principal de la aplicación web y un sitio poco confiable puede molestar a los clientes o desalentar su participación.   
•	Es difícil predecir la carga colocada en los servidores web por la aplicación web para compartir fotos porque solo podemos adivinar el número de clientes que podrían optar por participar en este punto del proyecto.   
•	La carga en los servidores web por la aplicación web para compartir fotos puede cambiar con poca antelación en determinadas épocas del año. Por ejemplo, después de Navidad, cuando se han vendido muchos productos nuevos, varios clientes nuevos pueden comenzar a participar en el intercambio de fotografías.   

## Casos de uso   

Los siguientes casos de uso describen escenarios en los que los clientes utilizan la aplicación web propuesta para compartir fotos. Todas las funciones básicas se han incluido en estos casos de uso, pero no deben considerarse definitivas. A medida que avanza el desarrollo, se pueden agregar funciones adicionales a discreción de los gerentes de proyecto.

### Caso de uso 1: examinar fotos

Cuando un visitante examina fotos en la aplicación web, se llevan a cabo los siguientes pasos:
1.	El visitante ingresa al sitio como un usuario anónimo en la página de inicio o puede hacer clic en el enlace de la Página de inicio en el menú.
2.	La página de inicio muestra miniaturas de las fotos agregadas más recientemente en la aplicación web. Para cada foto se muestra el título, el propietario y la fecha de creación.
3.	Si el usuario anónimo desea ver todas las fotos en el sitio, el usuario hace clic en el enlace Todas las fotos en el menú principal.
4.	La aplicación web muestra la galería de fotos con miniaturas de todas las fotos de la lista. Para cada foto se muestra el título, el propietario y la fecha de creación.
5.	Si el usuario anónimo desea ver una foto en tamaño completo, el usuario hace clic en la miniatura de la foto o en el enlace Detalles de esa foto.
6.	La aplicación web muestra la foto elegida a tamaño completo. También se muestran el título de la foto, el propietario, la descripción, la fecha de creación y los comentarios.

### Caso de uso 2: agregar un comentario a una foto

Solo los clientes autenticados deberían poder agregar comentarios a una foto. Cuando un cliente agrega un comentario a una foto, se llevan a cabo los siguientes pasos:
1.	El cliente hace clic en el enlace Detalles debajo de una foto o hace clic en una foto en la galería de fotos.
2.	La aplicación web muestra la foto elegida a tamaño completo. También se muestran el título de la foto, el propietario, la descripción, la fecha de creación y los comentarios existentes.
3.	El cliente hace clic en el enlace Agregar un comentario. Si el usuario ya ha iniciado sesión, la aplicación web muestra un formulario para los detalles de los comentarios.
4.	Si el usuario es anónimo, se muestra la página de inicio de sesión y el usuario proporciona las credenciales.
5.	Si las credenciales son correctas, la aplicación web muestra un formulario para los detalles de los comentarios.
6.	El usuario completa el contenido del tema y completa el contenido de su comentario.
7.	El usuario hace clic en Enviar.
8.	La aplicación web muestra la foto elegida a tamaño completo con todos los comentarios y otros detalles. El nuevo comentario se muestra en la parte inferior de la lista de comentarios con el nombre del usuario que lo creó.

### Caso de uso 3: agregar una foto

Cuando un cliente agrega una foto a la aplicación web, se llevan a cabo los siguientes pasos:
1.	El usuario hace clic en el enlace Agregar foto en el menú principal del sitio.
2.	Si el usuario es anónimo, se muestra la página de inicio de sesión y el usuario proporciona las credenciales.
3.	Si las credenciales son correctas, se muestra la página Crear foto.
4.	El usuario escribe un título.
5.	El usuario especifica el archivo de foto a cargar.
6.	El usuario escribe opcionalmente una descripción para la foto.
7.	El usuario hace clic en el botón Cargar.
8.	La aplicación web almacena la nueva foto y muestra la galería de fotos al usuario.

### Caso de uso 4: eliminar una foto

Cuando un cliente elimina una foto de la aplicación web, se llevan a cabo los siguientes pasos:
1.	El cliente hace clic en el enlace Iniciar sesión en cualquier página de la aplicación web.
2.	Se muestra la página de inicio de sesión y el usuario proporciona las credenciales.
3.	Si las credenciales son correctas, se muestra la página de inicio.
4.	El cliente hace clic en un enlace de Detalles o una foto en la galería de fotos.
5.	La aplicación web muestra la foto elegida a tamaño completo. También se muestran el título de la foto, el propietario, la descripción, la fecha de creación y los comentarios. Si el cliente está autenticado y el propietario de la foto actual tiene el mismo nombre de usuario que el cliente, se muestra el enlace Eliminar esta foto.
6.	El cliente hace clic en el enlace Eliminar esta foto.
7.	La aplicación web solicita confirmación.
8.	Si el cliente confirma la eliminación, la foto se elimina de la base de datos junto con todos los comentarios al respecto.
9.	La aplicación web muestra la galería de fotos al cliente.
 
Figura 1. Resumen de los casos de Uso





## Transcripción de las entrevistas con el usuario
El 20 de mayo de 2018, los Autores entrevistaron a Mark Alexieff, un cliente a largo plazo de Adventure Works. Es un fotógrafo entusiasta además de ciclista y está entusiasmado con la aplicación web propuesta. Los Autores han incluido esta entrevista aquí porque creemos que Mark tiene buenas ideas sobre cómo debe verse y comportarse la aplicación web, lo que puede guiar a los desarrolladores a medida que crean páginas web.

*Autores:* Háblenos de su bicicleta de montaña.   
*Mark Alexieff:* Llevo veinte años pilotando. Actualmente vivo en Albany, NY, y viajo todos los fines de semana, generalmente en Catskills pero a veces más lejos.   
*Autores:* ¿Y haces fotos?   
*MA:* ¡Sí! Supongo que he estado tomando fotos durante todo ese tiempo.   
*Autores:* ¿Solo instantáneas o algo más serio?   
*MA:* Bueno, trato de tomarlo en serio. Tengo una cámara réflex digital y disparo unas 50 tomas en un día normal. Obviamente, muchos paisajes, pero también me gusta hacer tomas de acción de mis amigos mientras viajan.   
*Autores:* ¿Compartes esas fotos en sitios de Internet?   
*MA:* Uso mucho Flickr, pero me interesaría usar un sitio solo para ciclistas de montaña.   
*Autores:* ¿Qué información le gustaría ver con cada foto?   
*MA:* La foto es lo más importante. Me gustaría ver que todo lo demás se reduzca al mínimo.   
*Autores:* ¿Pero seguramente necesitas saber quién tomó una foto y demás?   
*MA:* Sí, necesitas algunas cosas. Debería poder agregar un título a sus fotos y ese título debe ser muy claro siempre que se muestre la foto.   
*Autores:* ¿Tanto para miniaturas como para pantallas de tamaño completo?   
*MA:* Eso creo. Además, me gustaría ver quién tomó cada foto donde sea que se use. Otra información, como la fecha en la que se tomó, es menos importante, pero debería poder encontrarla cuando esté interesado.   
*Autores:* Correcto. ¿Qué más crees que te gustaría contarles a otros usuarios sobre tus fotos?   
*MA:* Bueno, creo que la mejor opción es aplicar una gran descripción. De esa forma, si quieres hablar sobre dónde se tomó la foto, quién está en ella, cómo estuvo el clima, puedes agregarla. Es bueno agregar un contexto como ese.   
*Autores:* ¿Le gustaría almacenar información técnica sobre la toma?   
*MA:* ¿Cómo qué?   
*Autores:* Estaba pensando en exposiciones, aperturas, ajustes de flash ...   
*MA:* Hablando por mí, no. Casi nunca grabo esas cosas en ese momento porque quiero seguir montando. Conozco fotógrafos que lo escriben religiosamente o lo obtienen de su cámara, pero yo no.   
*Autores:* ¿Entonces tal vez deberíamos proporcionar campos opcionales?   
*MA:* Ya hablamos sobre la disponibilidad de una descripción. Si alguien quiere compartir esa información, puede usarla, ¿no es así?   
*Autores:* Si. OKAY. ¿Te gustan los bordes alrededor de las fotos?   
*MA:* A veces. Depende de la foto. ¿Podrías darme una opción?   
*Autores:* Posiblemente. ¿Le gustaría poder elegir un color para su borde?   
*MA:* Casi siempre sería en blanco o negro en una aplicación web. O nada. También debe tener cuidado con los colores que usa.   
*Autores:* ¿De qué manera?   
*MA:* Trate de ser neutral. Si tiene un color de fondo brillante detrás de las fotos, realmente cambiará su impacto. De hecho, diría que no use un borde y haga que el color de fondo sea blanco o negro. Gray podría estar bien.   
*Autores:* OK. ¿Qué pasa con los comentarios ... te gustaría verlos a la derecha de una foto?   
*MA:* Debajo de la foto, definitivamente. La mayoría de las veces, no me interesan los comentarios. Solo leo comentarios si quiero saber dónde se rodó o los nombres de las personas en la foto. Algunas fotos me interesan más y luego puedo desplazarme hacia abajo para ver los comentarios. La mayoría de las veces, no quiero que los comentarios me distraigan.   

## Requerimientos técnicos

La aplicación web debe cumplir con los siguientes requisitos técnicos:

•	95% de tiempo de actividad: el sitio debe estar disponible al menos el 95% del tiempo. Cualquier actualización de software, cambios de hardware, fallas y desastres no deberían afectar esta disponibilidad mínima.   
•	Credenciales protegidas: los nombres de usuario y las contraseñas no deben intercambiarse en texto sin formato.   
•	Datos personales protegidos: los datos personales de los usuarios, como direcciones, números de teléfono y números de tarjetas de crédito, no deben estar disponibles para el acceso anónimo.   
•	Escalabilidad: aún no se ha realizado una estimación del número esperado de usuarios simultáneos o de la cantidad de datos que deben almacenarse. Sin embargo, la arquitectura utilizada para alojar la aplicación web debe ser capaz de escalar rápidamente para hacer frente a los tiempos en que un gran número de nuevos usuarios se registra y carga fotos.   
