# react_intro

### ¿Que es React.js?
ReactJS es una de las librerías más populares de JavaScript para el desarrollo de aplicaciones móviles y web. Creada por Facebook, React contiene una colección de fragmentos de código JavaScript reutilizables utilizados para crear interfaces de usuario (UI) llamadas componentes.
Es importante señalar que ReactJS no es un framework de JavaScript. Esto porque sólo es responsable de renderizar los componentes de la capa de vista de una aplicación. React es una alternativa a frameworks como Angular y Vue, que permiten crear funciones complejas.

## ¿Cuáles son las diferencias entre React.js versión 18?
La nueva versión de React trae consigo varios cambios y mejoras como por ejemplo: procesamiento por lotes automático (automatic batching), nuevas API comostartTransition, streaming SSR y un nuevo soporte para Suspense.

La gran mayoría de estas características son soportadas por un nuevo desarrollo escencial: “renderizado concurrente”. Un cambio interno que permite el desarrollo de nuevas y poderosas características de cara a los desarrolladores de aplicaciones y librerías.

### Routing (Enrutamiento):
Definición: El enrutamiento en React se refiere a la gestión de la navegación entre diferentes vistas o componentes de una aplicación. Permite que los usuarios naveguen entre diferentes partes de la aplicación sin tener que recargar la página completa.

### Rendering (Renderización):
Definición: La renderización en React se refiere al proceso de representar la interfaz de usuario en función del estado y los datos del componente. React utiliza un modelo de renderización declarativo, lo que significa que los desarrolladores describen la interfaz de usuario y React se encarga de actualizar la vista cuando el estado cambia.

### Data Fetching (Obtención de Datos):
Definición: En una aplicación React, a menudo es necesario recuperar datos de un servidor o de alguna fuente externa. La obtención de datos implica el uso de métodos como fetch o librerías como Axios para realizar solicitudes HTTP y obtener la información necesaria para mostrar en la interfaz de usuario.

### Styling (Estilización):
Definición: Este se refiere a la aplicación de estilos visuales a los componentes de React. Puede hacerse mediante CSS puro, preprocesadores como Sass o mediante soluciones de estilo en línea o de módulos CSS que permiten el acoplamiento de estilos con componentes específicos.

### Optimizations (Optimizaciones):
Definición: Las optimizaciones en React implican técnicas para mejorar el rendimiento y la eficiencia de una aplicación. Esto puede incluir la implementación de shouldComponentUpdate para evitar renderizaciones innecesarias, el uso de memoización con React.memo y otras estrategias para minimizar el costo computacional.

### TypeScript:
Definición: TypeScript es un superconjunto de JavaScript que agrega tipado estático a la sintaxis de JavaScript. Al utilizar TypeScript con React, se pueden definir tipos para los props y el estado de los componentes, proporcionando así una capa adicional de seguridad y herramientas de desarrollo mejoradas.
Estos términos representan diferentes aspectos de desarrollo al trabajar con React y se utilizan para describir y abordar diferentes partes de la construcción de una aplicación web.

### Componentes (Components):
Los componentes son bloques de construcción fundamentales en React. Representan partes reutilizables e independientes de la interfaz de usuario. Pueden contener tanto la lógica como la interfaz de usuario, y se pueden componer para construir aplicaciones más grandes. Los componentes en React pueden ser funcionales o basados en clases.

### JSX (JavaScript XML):
JSX es una extensión de sintaxis para JavaScript que permite escribir código que se parece al marcado HTML/XML. Facilita la definición de la interfaz de usuario en React de una manera más declarativa y legible. Aunque se asemeja al HTML, JSX se compila a llamadas de funciones de JavaScript y se utiliza para definir la estructura de los componentes React.

### Props (Propiedades):
Las propiedades son datos que se pasan de un componente padre a un componente hijo en React. Permiten la comunicación entre componentes y son inmutables, lo que significa que un componente hijo no puede modificar directamente las propiedades que recibe. Las props son una forma eficaz de pasar datos y configurar componentes de manera dinámica.

### Estado (State):
El estado es un objeto que contiene datos importantes para un componente. A diferencia de las props, el estado es mutable y se utiliza para gestionar información que puede cambiar durante la vida útil de un componente. Cuando el estado de un componente cambia, React se encarga de actualizar automáticamente la interfaz de usuario para reflejar esos cambios.

# patrón de diseño estructural Composite
El patrón de diseño estructural Composite se utiliza para componer objetos en estructuras de árbol para representar jerarquías parte-todo. Este patrón permite a los clientes tratar tanto a los objetos individuales como a las composiciones de objetos de manera uniforme. De esta manera, el Composite facilita la creación de estructuras complejas y anidadas, al tiempo que proporciona una interfaz consistente.

Componente (Component):
Define la interfaz común para todos los componentes (hojas y compuestos).
Declara las operaciones que deben ser implementadas tanto por las hojas como por los compuestos.

Hoja (Leaf):Representa los nodos finales de la estructura del árbol.
Implementa la interfaz del componente.
No tiene hijos.

Compuesto (Composite):
Define el comportamiento que se aplica a los componentes hijos.
Almacena componentes hijos.
Puede implementar operaciones adicionales específicas de la composición.
Cliente (Client):

Manipula objetos a través de la interfaz del componente.
Trata tanto a las hojas como a los compuestos de manera uniforme.

# patrón de diseño estructural State
l patrón de diseño estructural llamado "State" es un patrón que se utiliza para permitir que un objeto cambie su comportamiento cuando su estado interno cambia. Este patrón se centra en la gestión de los estados internos de un objeto y la transición entre estos estados. Al utilizar el patrón State, un objeto puede parecer cambiar de clase en tiempo de ejecución.

En el contexto de React, el patrón de diseño State se relaciona con la gestión del estado en los componentes. En React, el estado es un objeto que representa cómo debería renderizarse un componente y cómo debería comportarse. Cuando el estado de un componente cambia, React se encarga de volver a renderizar el componente para reflejar ese cambio en la interfaz de usuario.
// Importa la biblioteca React
import React, { Component } from 'react';

// Define un componente de ejemplo llamado MyComponent
class MyComponent extends Component {
  // Inicializa el estado del componente
  state = {
    // Define una propiedad en el estado llamada 'estadoActual' con el valor inicial 'Inicial'
    estadoActual: 'Inicial'
  };

  // Método para manejar un evento que cambia el estado
  handleCambioEstado = () => {
    // Cambia el estado utilizando el método setState
    this.setState({
      estadoActual: 'Modificado'
    });
  };

  // Renderiza el componente
  render() {
    return (
      <div>
        {/* Muestra el estado actual */}
        <p>Estado Actual: {this.state.estadoActual}</p>
        
        {/* Botón que, al hacer clic, invoca el método handleCambioEstado */}
        <button onClick={this.handleCambioEstado}>Cambiar Estado</button>
      </div>
    );
  }
}

// Exporta el componente para poder utilizarlo en otras partes de la aplicación
export default MyComponent;
