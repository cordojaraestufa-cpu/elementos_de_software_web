Parte 1: Investigación (Teoría)
1. ¿Qué es React?

React es una librería de JavaScript de código abierto, creada por Meta (Facebook) en 2013, que se utiliza específicamente para construir interfaces de usuario (UI), principalmente en aplicaciones de una sola página (SPAs o Single Page Applications).

A diferencia de los frameworks tradicionales que te imponen una estructura completa de trabajo, React se enfoca únicamente en la capa de la vista (lo que el usuario ve y toca en la pantalla).

Su magia se basa en dos pilares fundamentales:

Componentes: Permite dividir la interfaz en bloques de construcción independientes y reutilizables (como piezas de Lego). Por ejemplo, un botón, una barra de navegación o una tarjeta de producto pueden ser componentes individuales.

Enfoque declarativo: En lugar de decirle al navegador paso a paso cómo modificar el diseño cuando algo cambia (enfoque imperativo), tú diseñas cómo debe verse la interfaz según el estado actual de los datos, y React se encarga de actualizarla de forma eficiente.


2. ¿Por qué usar React?
Si ya existen HTML, CSS y JavaScript nativo, ¿por qué complicarse con React? Aquí tienes las razones principales por las que domina el mercado:

Reutilización de código: Creas un componente (por ejemplo, una tarjeta de perfil) una sola vez y lo puedes usar en diez partes distintas de tu aplicación, o incluso en proyectos diferentes. Esto ahorra muchísimo tiempo y mantiene el código limpio.

Rendimiento optimizado (Virtual DOM): Modificar el diseño directamente en el navegador (el DOM real) es un proceso lento. React crea una copia en memoria llamada Virtual DOM. Cuando algo cambia, React compara los cambios en memoria y solo actualiza la parte exacta de la pantalla que cambió, haciendo que la aplicación sea increíblemente rápida.

Gran ecosistema y comunidad: Al ser tan popular, si tienes un problema, lo más probable es que alguien ya lo haya solucionado. Además, hay miles de librerías complementarias para añadirle funciones de todo tipo (rutas, gestión de estados, animaciones).

React Native: Si aprendes React para la web, ya tienes el 80% del camino hecho para crear aplicaciones móviles nativas para iOS y Android usando React Native.

3. ¿Qué necesito saber antes?
Para que tu curva de aprendizaje no sea una tortura, es fundamental que domines ciertos temas antes de escribir tu primera línea en React. No necesitas ser un experto, pero sí sentirte cómodo con lo siguiente:

1. HTML y CSS (Esencial)
Debes entender la estructura de una página web (etiquetas, atributos) y cómo darle estilos (maquetación, flexbox o CSS Grid). React genera HTML a través de JavaScript, así que debes conocer las bases.

2. JavaScript Moderno (El verdadero motor)
React es JavaScript. Si intentas aprender React sin bases sólidas de JS, te vas a frustrar confundiendo qué es del lenguaje y qué es de la librería. Enfócate en:

Variables y tipos de datos: const y let.

Funciones flecha (Arrow Functions): Muy usadas para definir componentes y manejadores de eventos.

Métodos de arrays: Especialmente .map() (esencial para renderizar listas de datos) y .filter().

Desestructuración (Destructuring): Para extraer datos de objetos y arrays fácilmente.

Módulos de JS: Entender cómo funcionan import y export.

3. Conceptos básicos de la Terminal / Consola
No necesitas ser un hacker, pero sí saber abrir la terminal de tu computadora, navegar entre carpetas (cd) y ejecutar comandos básicos, ya que para instalar y correr proyectos de React usarás herramientas como Node.js y NPM (o Vite).

¿Cómo te sientes con estos prerrequisitos? Si estás listo, el siguiente paso natural es configurar tu entorno de desarrollo o ver un ejemplo de cómo luce el código en React.

PARTE 4

Aquí tienes las respuestas a tus preguntas de investigación sobre React, acompañadas de explicaciones claras y un código de ejemplo al final que conecta todos estos conceptos.

1. ¿Qué es JSX?
JSX significa JavaScript XML. Es una extensión de la sintaxis de JavaScript que permite escribir estructuras que se parecen mucho a HTML directamente dentro de tu código de React.

¿Para qué sirve? Hace que el código sea más visual y fácil de escribir o mantener.

Dato clave: Los navegadores no entienden JSX directamente. React utiliza herramientas (como Babel) para traducir este código JSX en funciones JavaScript estándar (React.createElement).

2. ¿Qué es un componente funcional?
En el React moderno, un componente funcional es literalmente una función de JavaScript que devuelve elementos de JSX (es decir, la interfaz de usuario que se va a mostrar en la pantalla).

Son los bloques de construcción de cualquier aplicación de React.

Pueden recibir datos de entrada (llamados props) y manejar su propio estado.

3. ¿Qué son los props en React?
La palabra props viene de properties (propiedades). Son la forma en que los componentes de React se pasan datos entre sí, específicamente de un componente padre a un componente hijo.

Son de solo lectura (inmutables): Un componente hijo nunca debe modificar las props que recibe; solo las usa para renderizar información.

Funcionan de manera similar a los argumentos de una función o a los atributos de una etiqueta HTML.

4. ¿Cómo se actualiza la pantalla automáticamente al cambiar datos?
React utiliza algo llamado Estado (State) y un mecanismo de renderizado reactivo.

Cuando los datos cambian dentro del estado de un componente, React detecta ese cambio automáticamente, calcula qué parte de la pantalla necesita actualizarse (usando un concepto llamado Virtual DOM) y vuelve a pintar solo ese fragmento en el navegador de forma ultra rápida, sin necesidad de recargar toda la página.

5. ¿Qué hace el useState?
useState es un Hook (una función especial de React) que te permite añadir un estado interno a un componente funcional.

Cuando declaras un useState, este te devuelve dos cosas en un arreglo:

La variable actual: El valor del dato que quieres guardar.

La función actualizadora: Una función que usas para cambiar ese valor. Cuando llamas a esta función, React sabe que debe actualizar la pantalla automáticamente.

Código de Ejemplo Completo
El siguiente ejemplo une todos los conceptos anteriores. Verás un componente padre (App) que le pasa una propiedad (prop) a un componente hijo (Contador), y este último usa useState para actualizar la pantalla al hacer clic.

JavaScript
import React, { useState } from 'react';

// 2. COMPONENTE FUNCIONAL (Hijo)

// 3. Recibe 'props' como argumento (en este caso, un título personalizado)
function Contador(props) {
  // 5. USO DE useState: 
  // 'clicks' es el dato actual (empieza en 0), 'setClicks' es la función para actualizarlo
  const [clicks, setClicks] = useState(0);

  const manejarClick = () => {
    // 4. Al usar setClicks, la pantalla se actualizará automáticamente
    setClicks(clicks + 1);
  };

  // 1. ESTO ES JSX: Mezcla de HTML y JavaScript
  return (
    <div style={{ border: '1px solid #ccc', padding: '20px', margin: '10px' }}>
      <h2>{props.titulo}</h2> {/* Usando la prop */}
      <p>Has hecho clic {clicks} veces</p> {/* Usando el estado */}
      <button onClick={manejarClick}>¡Hazme click!</button>
    </div>
  );
}

// COMPONENTE FUNCIONAL (Padre)
export default function App() {
  return (
    <div>
      <h1>Mi Aplicación de React</h1>
      {/* Renderizamos el componente hijo y le pasamos la prop 'titulo' */}
      <Contador titulo="Contador del Equipo A" />
      <Contador titulo="Contador del Equipo B" />
    </div>
  );
}

Entregables / Evaluación
¿Pudiste correr npm start?

r//claro que si solo que se demoro un poco


¿Modificaste el App.js?

r//s estuvo un poco complicado al inicio


¿Creaste tu primer componente?

r// claro que siii


¿Implementaste props? - Investiga que son los props
Las props (que viene de la palabra properties o propiedades en inglés) son la forma en que los componentes de React se pasan datos entre sí.


¿Hiciste el mini-proyecto del contador? - No te preocupes, solo era intentarlo.
R// siiiii

¿Investigaste los 5 puntos clave?
siii

