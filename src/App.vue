<template>
  <div id="app">
    <section class="mg-top-bot reducirespaciadosection">
      <b-container>
        <b-row class="centrar">
          <b-col class="ocultar-div" sm="12" md="4" style="padding-bottom: 30px">
           <div>
           </div>
          </b-col>
          <b-col class="sinborde" sm="12" md="8">
            <preguntasFrecuentesGenerico
            :preguntas=preguntas           
            :nombrepagina=TextoTab         
            :imagenMenu=imagenMenu
            :regresarPrincipal=regresarPrincipal
            :itemsMenu=itemsMenu
            />
          </b-col>
          
        </b-row>
         
      </b-container>
       
    </section>
    
  </div>
</template>

<script>
import preguntasFrecuentesGenerico from './components/preguntasFrecuentesGenerico.vue'

export default {
  name: 'App',
  components: {
    preguntasFrecuentesGenerico,
  },
  data () {
    return {
      TextoTab: 'Utilización del seguro seguro seguro seguro',
      imagenMenu: require("./static/media/icons/Group11Copy.svg"),
      regresarPrincipal: '/preguntas-frecuentes/',
      preguntas:[
          {
              id: '1',
              title: '¿Qué hacer en caso de Emergencias?',
              identificador: 'collapse-1',
              respuesta: [ 
                '<p class="parrafo omnes-medium">Es la central encargada de atender cualquier consulta que puedas tener respecto a tu seguro viaje, así como una respuesta ante accidentes o emergencias..</p>',
                '<img src="">'
                 ],
              
          },
          {
              id: '2',
              title: '¿Qué es la Central de Atención al Cliente?',
              identificador: 'collapse-2',
              respuesta: [ 
                '<p class="parrafo omnes-medium">Es la central encargada de atender cualquier consulta que puedas tener respecto a tu seguro viaje, así como una respuesta ante accidentes o emergencias..</p>',
                '<p class="parrafo omnes-medium">Para contactar con la Central de Asistencia deberás comunicarte a los siguientes números:.</p>',
                '<li class="anchorespuestas estiloparrafo omnes-medium">(01) 500-0000 0-801-00165 (Provincias)</li>',
                '<p class="parrafo omnes-medium">O al correo</p>',
                '<li class="anchorespuestas estiloparrafo omnes-medium">servicios@interseguro.com.pe</li>',
                '<p class="parrafo omnes-medium">*Es importante recalcar que para asistencia de viaje, se deberán recurrir a los números descritos en la sección “asistencia de viaje”.</p>'
                 ],
          },
          {
              id: '3',
              title: '¿A partir de cuándo puedo hacer uso de las asistencias?',
              identificador: 'collapse-3',
              respuesta: [ 
                '<p class="parrafo omnes-medium">A partir del momento de la fecha de vigencia del seguro podrás hacer uso de las asistencias.</p>',
                 ],
          },
          {
              id: '4',
              title: '¿Puedo solicitar el seguro si viajo por motivos no turísticos?',
              identificador: 'collapse-4',
              respuesta: [ 
                '<p class="parrafo omnes-medium">El propósito de tu viaje tendrá que ser turístico. En ningún momento podrá garantizar a personas que ejerzan una actividad profesional en el exterior. Si el motivo del viaje del Beneficiario fuese la ejecución de trabajos o tareas que involucren un riesgo profesional, por realizar tareas de alta especialización en donde se exponga la vida, se esté expuesto a:</p>',
                '<li class="anchorespuestas estiloparrafo omnes-medium">Sustancias peligrosas</li>',
                '<li class="anchorespuestas estiloparrafo omnes-medium">Manejo de maquinarias pesadas o que funcionan con gases</li>',
                '<li class="anchorespuestas estiloparrafo omnes-medium" style="margin-bottom:1rem;">Presión de aire o fluidos hidroneumáticos, que requieran habilidades físicas especiales</li>',
                '<p class="parrafo omnes-medium">o donde se vea expuesto a peligro y como consecuencia de ello sufra un accidente o una enfermedad consecuencial, Interseguro quedará eximido de toda responsabilidad de prestar sus servicios o asumir costos que se deriven de tales circunstancias, y en estos casos será obligación patronal de asumirlos a través de su plan de responsabilidad de riesgos profesionales.</p>'
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
          title: "Utilización del seguro seguro seguro seguro seguro",
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
      respuestas: []
    }
  },

  methods: {
  
  }
}
</script>

<style>
.collapsed > .when-opened,
:not(.collapsed) > .when-closed {
  display: none;
}

.mg-top-bot {
  margin: 3rem 0;
}

.linkprincipal {
  padding-left: 3px;
  padding-right: 8px;
  padding-bottom: 7px;
  padding-top: 7px;
  font-size: 14px;
  color: #9a9aa3;
}

.centrarpregunta {
  display: flex;
  align-items: center;
}

.opcionesdropdown {
  color: #0754c4 !important;
  font-size: 18px;
  font-weight: 400;
  line-height: 14px;
  text-align: center;
  padding: 9px;
  margin-left: 0px;
}

.movertitulodropdown {
  position: relative;
  top: 2px;
}

.tamañoflechadropdown {
  width: 15px;
  height: 8px;
}

.change {
  display: flex;
  justify-content: space-between;
}

.flecha {
  position: relative;
  left: -90px;
}

#banner-links .links-text:hover {
  text-decoration: none;
}

.principal {
  font-size: 14px;
  font-weight: 400;
  line-height: 18px;
  text-align: left;
  padding: 10px;
}

.titulopf {
  color: #0754c4;
  font-size: 30px;
  font-weight: 600;
  line-height: 16px;
  width: 521px;
  text-align: left;
  padding-top: 15px;
}

.subtitulo {
  color: #6f6f6f;
  font-size: 20px;
  font-weight: 500;
  text-align: left;
}

.linea {
  background-color: #d8d8d8;
  width: 653px;
  height: 2px;
}

.estiloparrafo {
  color: #6f6f6f;
  font-size: 16px;
  font-weight: 400;
  line-height: 30px;
  text-align: left;
  padding-top: 0px;
}

.lista {
  color: #6f6f6f;
  font-size: 18px;
  font-weight: 500;
  line-height: 24px;
  width: 550px;
  text-align: left;
}

.lista2 {
  color: #0754c4;
  font-size: 18px;
  font-weight: 500;
  line-height: 24px;
  width: 550px;
  text-align: left;
}

.linkazul {
  color: #0754c4;
  font-size: 18px;
  font-weight: 600;
  line-height: 16px;
  text-align: left;
}

a {
  text-decoration: none;
  color: #8b8b91;
}

.achicar {
  width: 1%;
  display: inline-block;
}

.quitarpunto {
  list-style: none;
  max-width: 20px;
}

ul.breadcrumb li + li:before {
  padding: 11px;
  color: black;
  content: "/\00a0";
}

a {
  text-decoration: none;
}

.moverizquierda {
  position: relative;
  right: 15px;
  padding-bottom: 4px;
}

.parrafo {
  color: #6f6f6f;
  font-size: 16px;
  font-weight: 400;
  line-height: 30px;
  width: 87%;
  text-align: left;
  padding-top: 0px;
}

.anchorespuestas {
  width: 640px;
}

@media screen and (max-width: 1200px) {
  .ocultar-div {
    display: none;
  }

  .izquierdadesplegable {
    display: flex;
    justify-content: space-between;
    align-content: center;
    align-items: center;
  }

  .titulodropdown {
    color: #0754c4;
    font-size: 25px;
    font-weight: 600;
    line-height: 16px;
    width: 521px;
    text-align: left;
  }

  .rectangulo {
    background-color: #ffffff;
    border-radius: 4.2px;
    box-shadow: 0 2px 6px 0 rgba(14, 90, 151, 0.5);
    width: 94%;
  }

  .flecha {
    position: relative;
    padding-right: 15px;
    left: 0px;
  }

  .centrar {
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .linea {
    background-color: #d8d8d8;
    width: 100%;
    height: 2px;
  }

  .parrafo {
    color: #6f6f6f;
    font-size: 16px;
    font-weight: 400;
    line-height: 30px;
    width: 96%; 
    text-align: left;
    padding-top: 0px;
  }

  .anchorespuestas {
    width: 585px;
  }
}

@media screen and (min-width: 1200px) {
  .ocultarmayor576px {
    display: none;
  }
}

@media screen and (max-width: 991px) {
  .parrafo {
    color: #6f6f6f;
    font-size: 16px;
    font-weight: 400;
    line-height: 30px;
    width: 96%;
    text-align: left;
    padding-top: 0px;
  }

  .lista {
    color: #6f6f6f;
    font-size: 18px;
    font-weight: 500;
    line-height: 24px;
    width: 409px;
    text-align: left;
  }

  .lista2 {
    color: #0754c4;
    font-size: 18px;
    font-weight: 500;
    line-height: 24px;
    width: 409px;
    text-align: left;
  }

  .parrafo {
    color: #6f6f6f;
    font-size: 16px;
    font-weight: 400;
    line-height: 30px;
    /* width: 435px; */
    text-align: left;
    padding-top: 0px;
  }

  .anchorespuestas {
    width: 435px;
  }
}

@media screen and (max-width: 767px) {

  .sinborde{ 
      padding-left: 0px;
      padding-right: 0px;
     }

  .acomodarlista {
    padding-left: 20px;
  }

  .parrafo {
    color: #6f6f6f;
    font-size: 16px;
    font-weight: 400;
    line-height: 30px;
    /* width: 525px; */
    text-align: left;
    padding-top: 0px;
    padding-left: 20px;
  }

  .anchorespuestas {
    width: 485px;
  }

  .estiloparrafo {
    color: #6f6f6f;
    font-size: 16px;
    font-weight: 400;
    line-height: 28px;
    text-align: left;
    padding-top: 0px;
    padding-left: 20px;
  }

  .moverizquierda {
    position: relative;
    right: 5px;
    padding-bottom: 4px;
  }
}

@media screen and (max-width: 540px) {
  .lista {
    color: #6f6f6f;
    font-size: 16px;
    font-weight: 500;
    line-height: 20px;
    width: 400px;
    text-align: left;
  }

  .lista2 {
    color: #0754c4;
    font-size: 16px;
    font-weight: 500;
    line-height: 20px;
    width: 400px;
    text-align: left;
  }

  .linkprincipal {
    padding-left: 5px;
    padding-right: 8px;
    padding-bottom: 7px;
    padding-top: 7px;
    font-size: 14px;
    color: #9a9aa3;
  }

  .subtitulo {
    color: #6f6f6f;
    font-size: 18px;
    font-weight: 500;
    text-align: left;
  }

  .reducirespaciadosection {
    margin-top: 18px;
  }

  .reducirpadding {
    padding-top: 8px;
  }

  .parrafo {
    color: #6f6f6f;
    font-size: 16px;
    font-weight: 400;
    line-height: 26px;
    /* width: 500px; */
    text-align: left;
    padding-top: 0px;
    padding-left: 20px;
  }

  .anchorespuestas {
    width: 465px;
  }

  .tamanonuevolink {
    font-size: 13px;
  }
}

@media screen and (max-width: 509px) {
  .rectangulo {
    background-color: #ffffff;
    border-radius: 4.2px;
    box-shadow: 0 2px 6px 0 rgba(14, 90, 151, 0.5);
    width: 94%;
    height: 60px;
  }

  .parrafo {
    color: #6f6f6f;
    font-size: 15px;
    font-weight: 400;
    line-height: 26px;
    /* width: 460px; */
    text-align: left;
    padding-top: 0px;
    padding-left: 20px;
  }

  .anchorespuestas {
    width: 430px;
    font-size: 15px;
  }

  .titulodropdown {
    color: #0754c4;
    font-size: 20px;
    font-weight: 600;
    line-height: 16px;
    width: 521px;
    height: 10px;
    text-align: left;
  }

  .tamañoiconodropdown {
    width: 40px;
    height: 38px;
  }
}

@media screen and (max-width: 490px) {
  .parrafo {
    color: #6f6f6f;
    font-size: 15px;
    font-weight: 400;
    line-height: 24px;
    /* width: 440px; */
    text-align: left;
    padding-top: 0px;
    padding-left: 20px;
  }

  .anchorespuestas {
    width: 420px;
    font-size: 15px;
  }
}

@media screen and (max-width: 469px) {
  .lista {
    color: #6f6f6f;
    font-size: 14px;
    font-weight: 500;
    line-height: 18px;
    width: 380px;
    text-align: left;
  }

  .lista2 {
    color: #0754c4;
    font-size: 14px;
    font-weight: 500;
    line-height: 18px;
    width: 380px;
    text-align: left;
  }

  .parrafo {
    color: #6f6f6f;
    font-size: 14px;
    font-weight: 400;
    line-height: 24px;
    /* width: 420px; */
    text-align: left;
    padding-top: 0px;
    padding-left: 20px;
  }

  .anchorespuestas {
    width: 390px;
    font-size: 14px;
  }
}

@media screen and (max-width: 455px) {
  .lista {
    color: #6f6f6f;
    font-size: 14px;
    font-weight: 500;
    line-height: 18px;
    width: 360px;
    text-align: left;
  }

  .lista2 {
    color: #0754c4;
    font-size: 14px;
    font-weight: 500;
    line-height: 18px;
    width: 360px;
    text-align: left;
  }

  .parrafo {
    color: #6f6f6f;
    font-size: 14px;
    font-weight: 400;
    line-height: 24px;
    /* width: 405px; */
    text-align: left;
    padding-top: 0px;
    padding-left: 20px;
  }

  .anchorespuestas {
    width: 375px;
    font-size: 14px;
  }
}

@media screen and (max-width: 440px) {
  .lista {
    color: #6f6f6f;
    font-size: 14px;
    font-weight: 500;
    line-height: 18px;
    width: 320px;
    text-align: left;
  }

  .lista2 {
    color: #0754c4;
    font-size: 14px;
    font-weight: 500;
    line-height: 18px;
    width: 320px;
    text-align: left;
  }

  .parrafo {
    color: #6f6f6f;
    font-size: 14px;
    font-weight: 400;
    line-height: 24px;
    /* width: 395px; */
    text-align: left;
    padding-top: 0px;
    padding-left: 20px;
  }

  .anchorespuestas {
    width: 365px;
    font-size: 14px;
  }
}

@media screen and (max-width: 425px) {
  .lista {
    color: #6f6f6f;
    font-size: 14px;
    font-weight: 500;
    line-height: 18px;
    width: 330px;
    text-align: left;
  }

  .lista2 {
    color: #0754c4;
    font-size: 14px;
    font-weight: 500;
    line-height: 18px;
    width: 330px;
    text-align: left;
  }

  .subtitulo {
    color: #6f6f6f;
    font-size: 17px;
    font-weight: 500;
    text-align: left;
  }

  .parrafo {
    color: #6f6f6f;
    font-size: 14px;
    font-weight: 400;
    line-height: 24px;
    /* width: 390px; */
    text-align: left;
    padding-top: 0px;
    padding-left: 20px;
  }

  .anchorespuestas {
    width: 360px;
    font-size: 14px;
  }
}

@media screen and (max-width: 400px) {
  .lista {
    color: #6f6f6f;
    font-size: 14px;
    font-weight: 500;
    line-height: 18px;
    width: 320px;
    text-align: left;
  }

  .lista2 {
    color: #0754c4;
    font-size: 14px;
    font-weight: 500;
    line-height: 18px;
    width: 320px;
    text-align: left;
  }

  .subtitulo {
    color: #6f6f6f;
    font-size: 16px;
    font-weight: 500;
    text-align: left;
  }

  .parrafo {
    color: #6f6f6f;
    font-size: 14px;
    font-weight: 400;
    line-height: 24px;
    /* width: 370px; */
    text-align: left;
    padding-top: 0px;
    padding-left: 20px;
  }

  .anchorespuestas {
    width: 340px;
    font-size: 14px;
  }
}

@media screen and (max-width: 381px) {
  .lista {
    color: #6f6f6f;
    font-size: 14px;
    font-weight: 500;
    line-height: 18px;
    width: 300px;
    text-align: left;
  }

  .lista2 {
    color: #0754c4;
    font-size: 14px;
    font-weight: 500;
    line-height: 18px;
    width: 300px;
    text-align: left;
  }

  .parrafo {
    color: #6f6f6f;
    font-size: 14px;
    font-weight: 400;
    line-height: 24px;
    /* width: 340px; */
    text-align: left;
    padding-top: 0px;
    padding-left: 20px;
  }

  .anchorespuestas {
    width: 310px;
    font-size: 14px;
  }
}

@media screen and (max-width: 359px) {
  .lista {
    color: #6f6f6f;
    font-size: 14px;
    font-weight: 500;
    line-height: 18px;
    width: 290px;
    text-align: left;
  }

  .lista2 {
    color: #0754c4;
    font-size: 14px;
    font-weight: 500;
    line-height: 18px;
    width: 290px;
    text-align: left;
  }

  .subtitulo {
    font-size: 15px;
  }

  .parrafo {
    color: #6f6f6f;
    font-size: 14px;
    font-weight: 400;
    line-height: 24px;
    /* width: 320px; */
    text-align: left;
    padding-top: 0px;
    padding-left: 20px;
  }

  .anchorespuestas {
    width: 295px;
    font-size: 13px;
  }
}

@media screen and (max-width: 349px) {
  .subtitulo {
    font-size: 15px;
  }

  .parrafo {
    color: #6f6f6f;
    font-size: 13px;
    font-weight: 400;
    line-height: 24px;
    /* width: 320px; */
    text-align: left;
    padding-top: 0px;
    padding-left: 20px;
  }

  .anchorespuestas {
    width: 300px;
    font-size: 13px;
  }

  .anchorespuestas {
    width: 285px;
    font-size: 13px;
  }
}

@media screen and (max-width: 338px) {
  .subtitulo {
    font-size: 14.5px;
  }

  .parrafo {
    color: #6f6f6f;
    font-size: 13px;
    font-weight: 400;
    line-height: 24px;
    /* width: 310px; */
    text-align: left;
    padding-top: 0px;
    padding-left: 20px;
  }

  .anchorespuestas {
    width: 280px;
    font-size: 13px;
  }

  .titulodropdown {
    color: #0754c4;
    font-size: 18px;
    font-weight: 600;
    line-height: 16px;
    width: 521px;
    height: 10px;
    text-align: left;
  }

  .tamañoiconodropdown {
    width: 35px;
    height: 32px;
  }
}

@media screen and (max-width: 330px) {
  .subtitulo {
    font-size: 14.5px;
  }

  .lista {
    color: #6f6f6f;
    font-size: 14px;
    font-weight: 500;
    line-height: 18px;
    width: 275px;
    text-align: left;
  }

  .lista2 {
    color: #0754c4;
    font-size: 14px;
    font-weight: 500;
    line-height: 18px;
    width: 275px;
    text-align: left;
  }

  .parrafo {
    color: #6f6f6f;
    font-size: 13px;
    font-weight: 400;
    line-height: 24px;
    /* width: 300px; */
    text-align: left;
    padding-top: 0px;
    padding-left: 20px;
  }

  .anchorespuestas {
    width: 270px;
    font-size: 13px;
  }
}
</style>
