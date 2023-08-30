# VUE3-COMPOSITION-API

Ejemplo de Interacción entre Componentes Padre-Hijo en Vue.js

Este repositorio contiene una aplicación simple en Vue.js que demuestra la interacción entre componentes padre-hijo utilizando props, eventos y el mecanismo provide / inject.
Componentes
App.vue

El componente principal que actúa como el padre de los componentes hijos.

    La plantilla incluye un título para el padre, un componente hijo HijoVue y otro componente hijo HijoVue2.
    El padre proporciona datos (nombre y edad) y un canal (miCanal) a sus componentes hijos.
    Se define un método cambiarValor para modificar los valores de nombre y edad.

Hijo.vue

Un componente hijo que recibe props y emite un evento para modificar datos en el componente padre.

    Muestra las props recibidas nombre y edad.
    Proporciona un botón que activa el método enviar, el cual emite un evento modificar al padre con nuevos valores.

Hijo2.vue

Otro componente hijo que accede a datos proporcionados por el componente padre mediante el mecanismo inject.

    Muestra el valor del canal inyectado.
    Proporciona un botón que activa el método modificar, cambiando el valor de canal.

Cómo Ejecutar

    Clona este repositorio: git clone <repository_url>
    Navega a la carpeta del proyecto: cd <repository_folder>
    Instala las dependencias: npm install o yarn install
    Ejecuta el servidor de desarrollo: npm run serve o yarn serve
    Abre tu navegador y ve a http://localhost:8080 para ver la aplicación en acción.

¡Siéntete libre de explorar y modificar los componentes para aprender más sobre las interacciones entre padres e hijos en Vue.js!
