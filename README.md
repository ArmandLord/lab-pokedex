![logo_ironhack_blue 7](https://user-images.githubusercontent.com/23629340/40541063-a07a0a8a-601a-11e8-91b5-2f13e4e6b441.png)

# Lab | React Native - Pokedex App

## Learning Goals

This exercise allows you to practice and apply the concepts and techniques taught in class.

Upon completion of this exercise, you will be able to:

- Install and use React Native Stack Navigator.
- Create a React Native app with multiple screens.
- Consumir la API de Pokemon para obtener información de los pokemons.
- Utilizar context y useReducer para manejar la información de los pokemons.
- Ver el detalle de un pokemon.
- Renderizar una lista de pokemons.
- Crear un formulario para añadir un nuevo pokemon a la lista.
- Crear los estilos de la aplicación.

## Introduction

En este lab vamos a crear una aplicación de React Native que nos permita ver una lista de pokemons y añadir nuevos pokemons a la lista y ver el detalle de cada pokemon. Para ello, vamos a utilizar la API de Pokemon <https://pokeapi.co/> y la libreria React Navigation <https://reactnavigation.org/> para crear la navegación entre pantallas.

## Requirements

- Fork this repo.
- Clone this repo.
- Run `nvm use` to use the node version specified into the `.nvmrc` file.

```bash
nvm use
```

- Install the dependencies.

```bash
npm install
```

- Start the project.

```bash
npm run ios
npm run android
```

## Submission

- Upon completion, run the following commands:

```bash
git add .
git commit -m "done"
git push origin master
```

- Create Pull Request so your TAs can check up your work.

## Example

This is how the app should looks like:

!TODO: Add GIF

## Instructions

### Iteration 1: Crear la estructura de la aplicación

- Crea una carpeta `src` en la raíz del proyecto.
- Crea una carpeta `navigation` en la raíz del proyecto.
- Crea una carpeta `components` dentro de `src`.
- Crea una carpeta `screens` dentro de `src`.
- Crea una carpeta `hooks` dentro de `src`.
- Crea una carpeta `context` dentro de `src`.

### Iteration 2: Crear la navegación

- Instala `Stack Navigator` de `React Navigation`.
- Crea un archivo dentro de `navigation` llamado `AppNavigator.js`.
- Crea un componente `AppNavigator` que renderice un `Stack Navigator` con tres pantallas: `Home`, `PokemonDetail` y `AddPokemon`.
- Crea la configuración de las rutas para cada pantalla.
- Utiliza el componente `AppNavigator` en `App.tsx`.

**Nota: No olvides tipar los props de `AppNavigator` con `PropTypes`**

### Iteration 3: Crear el contexto

- Configura el contexto de la aplicación. Recuerda utilizar `useReducer` para manejar el estado de la aplicación.
- Proporciona el contexto a la aplicación.

**Nota: No olvides crear todos los tipos necesarios para el contexto.**

### Iteration 4: Crear los screens

- Crea un componente `HomeScreen` que renderice un `SafeAreaView` con un `FlatList` que muestre la lista de pokemons.
- Crea un componente `PokemonDetailScreen` que renderice un `SafeAreaView` con la información del pokemon.
- Crea un componente `AddPokemonScreen` que renderice un `SafeAreaView` con un formulario para añadir un nuevo pokemon a la lista.

### Iteration 5: Obtener y renderizar la lista de pokemons

- Crea un hook `useFetch` que nos permita hacer peticiones a la API de Pokemon. (puedes utilizar axios.create para crear una instancia de axios con la url base de la API).
- Obten la lista de pokemons utilizando el hook `useFetch` y guárdala en el estado del contexto. Puedes utilizar el siguiente endpoint: <https://pokeapi.co/api/v2/pokemon?limit=151>
- Por ahora renderiza solo una lista de los nombres de pokemons en la pantalla `HomeScreen` utilizando el contexto.

**Nota: No olvides crear todos los tipos necesarios para el hook `useFetch`.**

### Iteration 6: Crear el componente PokemonList y PokemonCard

- Crea un componente `PokemonList` que reciba como prop la lista de pokemons y renderice un `FlatList` con los pokemons.
- Para el renderItem crea y utiliza un componente `PokemonCard` que reciba como prop el pokemon y renderice el nombre del pokemon, su número (id) y su imagen.
- Tip: Necesitaras crear una funcion que te permita obtener el id de un pokemon a partir de su url y puedes utilizar el siguiente endpoint para obtener la imagen de un pokemon: <https://pokeres.bastionbot.org/images/pokemon/${id}.png>
- Utiliza el componente `PokemonList` en la pantalla `HomeScreen`.

**Nota: El componente `PokemonCard` debe permitir al usuario navegar a la pantalla `PokemonDetailScreen` al hacer click sobre el.**

### Iteration 7: Obtener y renderizar el detalle de un pokemon

- Obtén la información de un pokemon utilizando el hook `useFetch` y guárdala en EL estado del contexto. Puedes utilizar el siguiente endpoint: <https://pokeapi.co/api/v2/pokemon/${id}>
- Utiliza el contexto para obtener la información del pokemon en la pantalla `PokemonDetailScreen` y renderiza su nombre, número (id), imagen, tipo y habilidades.
- Puedes crear un componente `PokemonDetail` para renderizar la información del pokemon o renderizarla directamente en la pantalla `PokemonDetailScreen`.
- Crea un botón que permita al usuario navegar a la pantalla `AddPokemonScreen` y asegurate que la navegacion entre pantallas funcione correctamente.

### Iteration 8: Crear el formulario para añadir un nuevo pokemon

- Crea un formulario en la pantalla `AddPokemonScreen` que permita al usuario añadir un nuevo pokemon a la lista.
- El formulario debe tener los siguientes campos: nombre, número (id), imagen, tipo y habilidades.
- Agrega validaciones a los campos del formulario.
- Al hacer submit del formulario, el nuevo pokemon debe añadirse a la lista de pokemons y enviar al usuario a la pantalla `HomeScreen`.
- Utiliza el contexto para añadir el nuevo pokemon a la lista y asegurate que la lista se actualice correctamente. Puedes crear un nuevo estado en el contexto para guardar el nuevo pokemon.

### Iteration 9: Crear los estilos de la aplicación

- Crea un archivo `theme.js` dentro de `src` y exporta un objeto con los colores de la aplicación.
- Crea un archivo `styles.js` dentro de `src` y exporta un objeto con los estilos de la aplicación.
- Los estilos quedan a tu elección, pero asegurate de que la aplicación se vea bien en iOS y Android. También puedes basarte en el diseño de la aplicación de ejemplo.

## Bonus:

- Crea un nuevo Screen `PokemonSearchScreen` que permita al usuario buscar un pokemon por su nombre o número (id).
- Integra Bottom Tabs Navigator para crear una navegación entre las pantallas `HomeScreen` y `PokemonSearchScreen`.

Happy coding! 💙
