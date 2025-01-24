# Conjunta2P


Descripción: 
Nuestra página funciona de la siguiente manera:
El usuario abre la página y ve una lista de libros disponibles, organizada con base en los 15 libros iniciales precargados en el sistema.
Cuando decide qué libro quiere que le presten, selecciona el botón correspondiente en la interfaz de "Prestar Libro", e ingresa el ID del libro en el prompt que aparece. Este libro se mueve de la lista de "libros disponibles" al array librosPrestados, actualizando automáticamente ambas listas en pantalla.
Si el usuario decide devolver un libro, selecciona su ID en el prompt desde la sección "Libros Prestados". El libro se regresa a la lista de "libros disponibles". Estas acciones son realizadas con botones asociados a funciones específicas en el sistema.


1. Estructura del sistema de préstamos: ¿Cómo organizar y manipular los libros prestados usando
arrays y sus métodos (push, pop, shift, unshift, splice)?

Los arrays libros y librosPrestados nos ayudan a organizar los libros disponibles y los prestados.
El push agrega libros al array  librosPrestados.
El splice se usa para eliminar libros de librosPrestados al devolverlos.
El find permite la búsqueda de un libro específico en el array.

Los procesos de préstamo y devolución actualizan dinámicamente las listas y utilizan arrays con métodos push, splice y find.
//librosPrestados.push(libro);

2. Filtrado y búsquedas dinámicas: ¿Cómo implementar filtros (filter) y búsqueda de libros por título,
autor o género?

La función buscarLibros usa filter para filtrar libros por título, autor o género.

//buscarLibros("titulo", "1984"); 

3. Interacción con el usuario: ¿Cómo mostrar la lista de libros disponibles y los libros prestados
usando manipulación del DOM (getElementById, querySelectorAll)?

Mediante el uso del DOM se muestra los libros disponibles mediante 
Se usa innerHTML y createElement para actualizar en el mismo tiempo las listas de libros y libros prestados.

4. Alertas y recordatorios: ¿Cómo enviar recordatorios automáticos de devolución usando setTimeout
o setInterval?

En esta seccion usamos setInterval para envíar recordatorios constantes sobre la devolución.

function enviarRecordatorio() {
      setInterval(() => {
        librosPrestados.forEach((libro) => {
          console.log(`Recordatorio: Devuelve el libro "${libro.titulo}" a tiempo.`);
        });
      }, 60000); // Cada minuto
    }

5. Eventos y usabilidad: ¿Cómo mejorar la experiencia del usuario con eventos (onclick, onchange, onmouseover, onmouseout, onfocus, onblur)?

El onclick es usado para responder al hacer clic en botones.
El prompt solicita el ID del libro.

  const id = parseInt(prompt("Introduce el ID del libro a prestar:"));



6. Funciones avanzadas: ¿Cómo usar funciones autoejecutables, anónimas, y async/await para
manejar procesos asíncronos?

Para este caso usamos await para manejar este proceso de notificar la disponibilidad sin que ocurra al mismo tiempo que otro proceso 
(async function notificarDisponibilidad() {
  await new Promise((resolve) => setTimeout(resolve, 5000));
  console.log("Notificación: Un libro reservado ahora está disponible.");
})();

7. Simulación de procesos asíncronos: ¿Cómo implementar la reserva y devolución de libros usando
promesas y setTimeout para simular tiempos de espera?

Las promesas y el metodo de setTimeout simulan el tiempo en que se deora estos procesos, en este caso son 3000 milisegundos, es decir, 3 segundos

//setTimeout(() => notificarUsuario("El libro reservado está disponible para su retiro."), 3000); 