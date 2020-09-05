# preguntas-frecuentes

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).


### 1er Paso: Instalar el paquete 📋
```
npm i preguntas-frecuentes-viajes
```

### 2do Paso: Importar en el archivo .vue donde quiera utilizar el componente :octocat:
```
import { preguntasFrecuentesGenerico } from 'preguntas-frecuentes-viajes'

export default {
    components: {
      preguntasFrecuentesGenerico
    }
}
```

### 3er Paso: Ingresar los datos requeridos :octocat:
```
<preguntasFrecuentesGenerico"
 :preguntas="preguntas"                                 <!-- Array con preguntas -->
 :itemsMenu="itemsMenu"                                 <!-- Los items que iran en el Menú desplegable -->
 :imagenMenu="imagenMenu"                               <!-- La imagen que ira en el menú desplegable -->
 :regresarPrincipal="regresarPrincipal"                 <!-- Ruta del breadcrumb -->
 :nombrepagina="TextoTab"                               <!-- Nombre de la pagina actual -->
/>

data () {
    return {
      TextoTab: 'Utilización del seguro',
      imagenMenu: require("@/static/media/icons/Group2Copy.svg"),
      regresarPrincipal: '/preguntas-frecuentes/',
      preguntas:[
          {
              id: '1',
              title: '¿Qué hacer en caso de Emergencias?',
              identificador: 'collapse-1',
              respuesta: [ 
                '<p class="parrafo omnes-medium">Soy un parrafo</p>',
                '<img src="">'
                 ],
              
          },
          {
              id: '2',
              title: '¿Qué es la Central de Atención al Cliente?',
              identificador: 'collapse-2',
              respuesta: [ 
                '<p class="parrafo omnes-medium">Soy un parrafo</p>',
                '<p class="parrafo omnes-medium">Soy un parrafo</p>',
                '<li class="anchorespuestas estiloparrafo omnes-medium">Soy una lista</li>',
                '<p class="parrafo omnes-medium">Soy un parrafo</p>',
                '<li class="anchorespuestas estiloparrafo omnes-medium">Soy una lista</li>',
                '<p class="parrafo omnes-medium">*Soy un parrafo”.</p>'
                 ],
          },
          {
              id: '3',
              title: '¿A partir de cuándo puedo hacer uso de las asistencias?',
              identificador: 'collapse-3',
              respuesta: [ 
                '<p class="parrafo omnes-medium">Soy un parrafo</p>',
                 ],
          },
          {
              id: '4',
              title: '¿Puedo solicitar el seguro si viajo por motivos no turísticos?',
              identificador: 'collapse-4',
              respuesta: [ 
                '<p class="parrafo omnes-medium">Soy un parrafo</p>',
                '<li class="anchorespuestas estiloparrafo omnes-medium">Soy una lista</li>',
                '<li class="anchorespuestas estiloparrafo omnes-medium">Soy una lista</li>',
                '<li class="anchorespuestas estiloparrafo omnes-medium" style="margin-bottom:1rem;">Soy una lista</li>',
                '<p class="parrafo omnes-medium">Soy un parrafo</p>'
                 ],
          },
      ],
      itemsMenu: [
        {
          id: "1",
          title: "Preguntas mas frecuentes",
          to: '/preguntas-frecuentes/'
        },
        {
          id: "2",
          title: "Planes Viaje Seguro",
          to: '/preguntas-frecuentes/planes-viaje-seguro'
        },
        {
          id: "3",
          title: "Como comprar Viaje Seguro",
          to: '/preguntas-frecuentes/como-comprar-viaje-seguro'
        },
        {
          id: "4",
          title: "Cobertura de Viaje Seguro",
          to: '/preguntas-frecuentes/cobertura-viaje-seguro'
        },
        {
          id: "5",
          title: "Modificación de Viaje Seguro",
          to: '/preguntas-frecuentes/modificacion-viaje-seguro'
        },
        {
          id: "6",
          title: "Utilización del seguro",
          to: '/preguntas-frecuentes/utilizacion-viaje-seguro'
        },
        {
          id: "7",
          title: "Trámites",
          to: '/preguntas-frecuentes/tramites'
        },
        {
          id: "8",
          title: "Sobre el COVID-19",
          to: '/preguntas-frecuentes/sobre-covid-19'
        }
      ],
    }
  },
```

### 4to Paso: Tener las imágenes correspondientes en la siguiente ruta📋
```
src/static/media/icons
```

![Captura de pantalla de 2020-07-03 20-23-41](https://user-images.githubusercontent.com/31213239/86502671-4f6e4b00-bd6b-11ea-9dac-7d7854d0c046.png)


### Observaciones

```
Las etiquetas 'img' funcionan con imagenes http
```

