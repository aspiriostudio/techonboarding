# Aspirio Tech On Boarding

## Next.js

## Tailwind

## MongoDB

## Git

Debes conocer y saber usar con confianza Git.

Git es un Sistema de Control de Versiones (CVS en inglés). Con él, puedes trabajar en equipo. Varias personas pueden trabajar sobre un mismo proyecto sin interferir unos con otros.

Para ello, Git provee las herramientas necesarias para gestionar tus tareas de la forma más eficiente posible. Te permite trabajar en una rama aislado en tu tarea, sin que el trabajo de otros interfiera en el tuyo, y sin que tu trabajo actual interfiera en el de otros.

La hora de la verdad aparece cuando un trabajo está finalizado y hay que unir las diferentes ramas.

Principios básicos:

1. La rama "main" (en versiones antiguas, se llamaba "master"), es la rama de producción. Esta rama es la más importante, ya que el funcionamiento correcto de la plataforma depende del código que haya en ella.

2. La rama "main" sólo aceptará nuevo código que provenga de la rama "develop".

3. La rama "develop" es la rama de desarrollo, paralela a main. Sobre esta rama se abrirán todas las ramas de las tareas, y al finalizar las tareas, se unirán a la rama develop. La rama develop es el estado de pre-producción o staging, donde se testearán los nuevos cambios antes de pasar a producción.

4. El estado de la rama develop es, en un futuro, el estado que tendrá la rama main (production). El código que entre en la rama develop será debidamente testeado, deberá pasar por todos los controles de calidad: linter, unit testing, deployment.

Este paso podrá ser automatizado más adelante con GitHub Actions.

5. Todas las nuevas tareas que se lleven a cabo comienzan creando una nueva rama que salga desde la última versión funcional de develop. Antes de comenzar una tarea asegúrate de estar situado en develop, en el último commit.

6. Todas las tareas, una vez finalizadas, se realizará un pull request a la rama develop. Antes de su integración a develop, se realizarán los tests pertinentes.

7. Si existe un conficto a la hora de hacer un merge de tu tarea con la rama develop, deberá ser resuelto en la propia rama antes de realizar el pull request.

8. Si la tarea toma demasiado tiempo desde que salió de develop, y la rama develop sigue avanzando, es responsabilidad de la persona que lleva a cabo la tarea ir integrando los cambios de develop en su rama, para que a la hora de hacer el merge no hayan conflictos.

9. En un principio siempre se realizarán "merges", nunca rebases o squases en la rama develop. De ese modo podemos tener un mayor insight del estado de desarrollo de las ramas, sin "cabezas sueltas", y podremos visualizar en el grafo el momento de integración para detectar posibles problemas.

10. La rama master estará bloqueada para evitar que se hagan commits accidentales en producción. La rama master cada vez que recibe un nuevo cambio, ejecuta un deploy automático en producción, por lo que no nos permitiremos errores innecesarios que derrumben la plataforma.

11. Es responsabilidad de cada persona saber solucionar los conflictos con su rama.

12. Si una tarea queda inacabada o abandonada, porque ha surgido una tarea con mayor urgencia, se dejarán todos los cambios en la rama de la tarea, se acudirá a develop, haremos un pull para tener la última versión, y de ahí surgirá una nueva rama para la nueva tarea. Bajo ningún concepto se debe abrir la rama de una nueva tarea sobre la rama de otra tarea.

13. Si no sabes resolver un problema que tengas con Git, acude a la documentación oficial. Git está ampliamente documentado en todos los idiomas. Nunca tomes una decisión que rompa la estructura de árbol de git, ni soluciones un problema parcheando el problema, porque al final se introduce un nuevo problema. Si la rama está mal, vuelve átras, comienza de nuevo, y resuelve el problema de raíz, como si nunca hubiese existido. Los errores que dejes por el camino se acaban pagando tarde o temprano.

14. Nunca fuerces un push que sobreescriba el árbol. Sigue el flujo del árbol. Si encuentras conflictos, usa los comandos que los resuelven.

15. Ante un conflicto que te haga determinar si tu código va a sustituir el de un compañero, consúltalo con el compañero. Si no tienes posibilidad de consultarlo, tendrás que tomar las riendas y arreglar el resultado para que ambos códigos coexistan. Si no existe posible solución, consulta el problema con el CTO para que lo revise.

16. Repito: Git está ampliamente documentado. Para cualquier problema que te encuentres, existe un procedimiento / comandos en Git para sobrellevarlo. Es tu responsabilidad conocerlos, o en su defecto, documentarte sobre qué se debería hacer al respecto. Cuando el procedimiento afecte al trabajo de otro compañero, tendrás que evitar seguir y consultarlo con el compañero y/o el CTO.

17. Es importante tener siempre en perspectiva global del estado del proyecto. Ten siempre ayuda de un software que te muestre el grafo del proyecto, tienes que saber siempre en qué lugar del árbol te encuentras en cada momento.

18. Utilizar git por comandos ciega. Muchas veces ocurrirá que el resultado no sea el que tu esperabas, a pesar de haber teclado los comandos que se suponían ser "los correctos". Utiliza el grafo visual para ver en perspectiva cómo ha quedado el árbol después de tu contribución, y sobre todo, antes de subir los cambios al repositorio. Comprueba siempre que el resultado es el que esperabas, y cómo va a quedar en GitHub antes de subirlo.

19. Evita subir información sensible al repositorio, como claves de APIs, contraseñas de bases de datos... es otra de las consecuencias de abusar de los comandos de consola, y de no corroborar el resultado antes de hacer el push.

20. Haz commits frecuentes, con sentido propio, y con mensajes explicativos. Es muy mala práctica realizar toda la tarea de golpe, y subir todos los cambios en un solo commit. El historial de cambios se convierte en un caos, y es dificil encontar problemas. Tampoco es buena práctica subir micro-cambios o "un commit por línea". Divide la tarea en pasos, y cada vez que finalices un paso: commit y push. Tu rama es parte de la historia de la evolución del proyecto, piensa que un nuevo desarrollador podría acudir a tu rama para ver cómo finalizaste con éxito una tarea, y la misma rama debería documentar de forma coherente y secuencial todos los pasos que seguiste, de modo que él podría aprender de ello.