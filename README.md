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



### 1er Paso: Importar en el archivo .vue donde quiera utilizar el componente📋
```
import { preguntasFrecuentesGenerico } from 'preguntas-frecuentes-alexander'

export default {
    components: {
      preguntasFrecuentesGenerico
    }
}
```

### 2do Paso: Ingresar los datos requeridos :octocat: 
```
<preguntasFrecuentesGenerico
 :preguntas=preguntas
 :nombrepagina=TextoTab
 :itemsMenu=itemsMenu
/>

data() {
    return {
      TextoTab:'Utilización del seguro',
      preguntas:[
          {
              id: '1',
              title: '¿Qué hacer en caso de Emergencias? ',
              identificador: 'collapse-1',
              respuesta: 'Respuesta Respuesta Respuesta Respuesta Respuesta1111111111111'
          },
          {
              id: '2',
              title: '¿Qué es la Central de Atención al Cliente?',
              identificador: 'collapse-2',
              respuesta: 'Respuesta Respuesta Respuesta Respuesta Respuesta2'
          },
          {
              id: '3',
              title: '¿A partir de cuándo puedo hacer uso de las asistencias?',
              identificador: 'collapse-3',
              respuesta: 'Respuesta Respuesta Respuesta Respuesta Respuesta3'
          },
          {
              id: '4',
              title: '¿Puedo solicitar el seguro si viajo por motivos no turísticos?',
              identificador: 'collapse-4',
              respuesta: 'Respuesta Respuesta Respuesta Respuesta Respuesta4'
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
  }
```

### 3er Paso: Tener las imágenes correspondientes en la siguiente ruta📋
```
src/static/media/icons
```

![Captura de pantalla de 2020-07-03 20-23-41](https://user-images.githubusercontent.com/31213239/86502671-4f6e4b00-bd6b-11ea-9dac-7d7854d0c046.png)


---
⌨️ con ❤️ por [AlexanderPrincipe](https://github.com/AlexanderPrincipe) 😊

