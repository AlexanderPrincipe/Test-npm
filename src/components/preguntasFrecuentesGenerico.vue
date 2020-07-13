<template lang="pug">
    div
        div.moverizquierda
          b-breadcrumb-item.achicar.quitarpunto(to="/preguntas-frecuentes/")
            img.d-inline.w-1(src="@/static/media/icons/PathCopy3.png")
          <router-link to="/preguntas-frecuentes/">
            span.omnes-medium.linkprincipal Principal
          </router-link>   
          span.omnes-medium(style="padding-right:6px;") ›
          span.omnes-semibold.tamanonuevolink(style="color: #0754C4;") {{nombrepagina}}

        div.pd-top-bot.reducirpadding
                h5.omnes-medium.titulo.ocultar-div(style="padding-bottom:15px") {{nombrepagina}}
                div.centrar
                    div.ocultarmayor576px.centrar.rectangulo(style="margin-bottom:20px; margin-top:0px")
                        <b-dropdown class="m-2" menu-class="w-100" style="width:100%;" variant="white" toggle-class="text-decoration-none" no-caret>
                            <template v-slot:button-content>       
                                div.izquierdadesplegable   
                                    span
                                        img.tamanoiconodropdown(src="@/static/media/icons/Group11Copy.svg" style="width:2rem;")
                                        span.movertitulodropdown.titulodropdown.omnes-medium(style="padding-left:10px;padding-right:20px;") {{nombrepagina}}
                                    span
                                        img.tamanoflechadropdown(src="@/static/media/icons/arrow_down.png")
                            </template> 
                                b-dropdown-item.opcionesdropdown(style="font-family: Omnes Medium" :to="item.to" v-for="(item, index) in itemsMenu" :key="index") {{item.title}}
                        </b-dropdown>
              
                div.linea
                div(v-for="(item, index) in preguntas" :key="index")             
                    div.centrarpregunta.change(v-b-toggle="item.identificador" style="height:64px;") 
                        div.lista2.omnes-semibold.when-opened.acomodarlista {{item.title}} 
                        div.lista.omnes-medium.when-closed.acomodarlista {{item.title}} 
                        img.when-opened.flecha.tamanoflecha2(src="@/static/media/icons/arrow_up.png")
                        img.when-closed.flecha.tamanoflecha2(src="@/static/media/icons/arrow_down.png")
                    b-collapse.mt-2(:id="item.identificador")
                        span(v-for="(subrespuesta, index) in item.respuesta")
                          span(v-html="subrespuesta")
                          
                    div.linea
           
</template>

<script>

export default {
  name: 'preguntasFrecuentesGenerico',
  props: {
    preguntas: {
      type: Array,
    },
    itemsMenu: {
      type: Array,
    },
    nombrepagina: String,
  },
  data() {
    return {
      
    };
  },
  mounted() {
    this.agregar();
    this.items.push(this.item);
  },
  methods: {
    agregar() {
      this.item = ['<p>Hola, soy un parrafo<p/>', '<p>Hola soy otro parrafo<p/>'];
      this.items.push(this.item);
    }
  }

};
</script>

<style scoped>

    .collapsed > .when-opened,
    :not(.collapsed) > .when-closed {
        display: none;
    }

    .pd-top-bot {
      padding: 14px 0;
    }

    .linkprincipal {
      padding-left:3px;
      padding-right:6px;
      padding-bottom:7px;
      padding-top:7px; 
      font-size: 14px;
      color:#9A9AA3;
    }

    .centrarpregunta {
       display: flex;
       align-items: center;
     }

  .opcionesdropdown {
      color: #0754C4 !important;
      font-size: 18px;
      font-weight: 400;
      line-height: 14px;
      text-align: center;
      padding:9px;
      margin-left: 0px;
    }

    .tamanoflecha2 {
      width:18px; 
      height:10px;
    }

  .movertitulodropdown {
      position: relative;
      top: 2px;
    }

    .tamanoflechadropdown {
      width:15px; 
      height:8px;
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


.titulo {
  color: #0754C4;
  font-size: 30px;
  font-weight: 600;
  line-height: 16px;
  width: 521px;
  text-align: left;
  padding-top: 15px;
}

.subtitulo {
  color: #6F6F6F;
  font-size: 20px;
  font-weight: 500;
  text-align: left;
}

.linea {
  background-color:#D8D8D8;
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
  color: #6F6F6F;
  font-size: 18px;
  font-weight: 500;
  line-height: 24px;
  width: 550px;
  text-align: left;
}

.lista2 {
  color: #0754C4;
  font-size: 18px;
  font-weight: 500;
  line-height: 24px;
  width: 550px;
  text-align: left;

}


  .linkazul {
    color: #0754C4;
    font-size: 18px;
    font-weight: 600;
    line-height: 16px;
    text-align: left;
  }

  a {
    text-decoration: none;
    color: #8B8B91;
  }

  .achicar {
    width: 1.8%;
    display: inline-block;
  }

  .quitarpunto {
    list-style:none;
    max-width: 20px;
  }

  ul.breadcrumb li+li:before {
    padding: 11px;
    color: black;
    content: "/\00a0";
  }

  a {
  text-decoration:none;
  }

  .moverizquierda {
    position: relative;
    right: 0px;
    padding-bottom: 4px;
  }

  .parrafo {
    color: #6f6f6f;
    font-size: 16px;
    font-weight: 400;
    line-height: 30px;
    width: 640px;
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
      color: #0754C4;
      font-size: 25px;
      font-weight: 600;
      line-height: 16px;
      width: 521px;
      text-align: left;
    }

    .tamanoflecha2 {
      width: 33px;
      height: 10px;
    }

    .rectangulo {
      background-color: #FFFFFF;
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
      background-color:#D8D8D8;
      width: 100%;
      height: 2px;
    }

    .parrafo {
      color: #6f6f6f;
      font-size: 16px;
      font-weight: 400;
      line-height: 30px;
      width: 585px;
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
      color: #6F6F6F;
      font-size: 18px;
      font-weight: 500;
      line-height: 24px;
      width: 409px;
      text-align: left;
    }

    .lista2 {
      color: #0754C4;
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
      width: 435px;
      text-align: left;
      padding-top: 0px;
    }
    
  .anchorespuestas {
      width: 435px;
  }

  .achicar {
    width: 2.1%;
    display: inline-block;
  }

   }


    @media screen and (max-width: 767px) {

     .lineas100{ 
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
      width: 525px;
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
      right: -10px;
      padding-bottom: 4px;
    }

    


   }

   @media screen and (max-width: 540px) {

    .lista {
      color: #6F6F6F;
      font-size: 16px;
      font-weight: 500;
      line-height: 20px;
      width: 400px;
      text-align: left;
    }

    .lista2 {
      color: #0754C4;
      font-size: 16px;
      font-weight: 500;
      line-height: 20px;
      width: 400px;
      text-align: left;
    }

    .linkprincipal {
      padding-left:5px;
      padding-right:6px;
      padding-bottom:7px;
      padding-top:7px; 
      font-size: 14px;
      color:#9A9AA3;
    }

    .subtitulo {
      color: #6F6F6F;
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
      width: 500px;
      text-align: left;
      padding-top: 0px;
      padding-left: 20px;
    }
    
    .anchorespuestas {
        width: 465px;
    }

    .tamanonuevolink{ 
      font-size: 13px;
    } 
   }

   @media screen and (max-width: 509px) {

    .rectangulo {
      background-color: #FFFFFF;
      border-radius: 4.2px;
      box-shadow: 0 2px 6px 0 rgba(14, 90, 151, 0.5);
      width: 94%;
      height: 60px;
    }

    .tamanoflecha2 {
      width: 30px;
      height: 8px;
    }

    .parrafo {
      color: #6f6f6f;
      font-size: 15px;
      font-weight: 400;
      line-height: 26px;
      width: 460px;
      text-align: left;
      padding-top: 0px;
      padding-left: 20px;
    }
    
    .anchorespuestas {
      width: 430px;
      font-size: 15px;
    }

    .titulodropdown {
      color: #0754C4;
      font-size: 20px;
      font-weight: 600;
      line-height: 16px;
      width: 521px;
      height: 10px;
      text-align: left;
    }

    .tamanoiconodropdown {
      width:40px; 
      height:38px;
  } 

   }

    @media screen and (max-width: 490px) {

    .parrafo {
      color: #6f6f6f;
      font-size: 15px;
      font-weight: 400;
      line-height: 24px;
      width: 440px;
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

    .tamanoflecha2 {
      width: 26px;
      height: 6px;
    }

    .lista {
      color: #6F6F6F;
      font-size: 14px;
      font-weight: 500;
      line-height: 18px;
      width: 380px;
      text-align: left;
    }

    .lista2 {
      color: #0754C4;
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
      width: 420px;
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
      color: #6F6F6F;
      font-size: 14px;
      font-weight: 500;
      line-height: 18px;
      width: 360px;
      text-align: left;
    }

    .lista2 {
      color: #0754C4;
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
      width: 405px;
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
      color: #6F6F6F;
      font-size: 14px;
      font-weight: 500;
      line-height: 18px;
      width: 320px;
      text-align: left;
    }

    .lista2 {
      color: #0754C4;
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
      width: 395px;
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
      color: #6F6F6F;
      font-size: 14px;
      font-weight: 500;
      line-height: 18px;
      width: 330px;
      text-align: left;
    }

    .lista2 {
      color: #0754C4;
      font-size: 14px;
      font-weight: 500;
      line-height: 18px;
      width: 330px;
      text-align: left;
    }

    .subtitulo {
      color: #6F6F6F;
      font-size: 17px;
      font-weight: 500;
      text-align: left;
    }

    .parrafo {
      color: #6f6f6f;
      font-size: 14px;
      font-weight: 400;
      line-height: 24px;
      width: 390px;
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
      color: #6F6F6F;
      font-size: 14px;
      font-weight: 500;
      line-height: 18px;
      width: 320px;
      text-align: left;
    }

    .lista2 {
      color: #0754C4;
      font-size: 14px;
      font-weight: 500;
      line-height: 18px;
      width: 320px;
      text-align: left;
    }

    .subtitulo {
      color: #6F6F6F;
      font-size: 16px;
      font-weight: 500;
      text-align: left;
    }

    .parrafo {
      color: #6f6f6f;
      font-size: 14px;
      font-weight: 400;
      line-height: 24px;
      width: 370px;
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
      color: #6F6F6F;
      font-size: 14px;
      font-weight: 500;
      line-height: 18px;
      width: 300px;
      text-align: left;
    }

    .lista2 {
      color: #0754C4;
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
      width: 340px;
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
      color: #6F6F6F;
      font-size: 14px;
      font-weight: 500;
      line-height: 18px;
      width: 290px;
      text-align: left;
    }

    .lista2 {
      color: #0754C4;
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
      width: 320px;
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
      width: 320px;
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
      width: 310px;
      text-align: left;
      padding-top: 0px;
      padding-left: 20px;
    }
    
    .anchorespuestas {
      width: 280px;
      font-size: 13px;
    }

    .titulodropdown {
      color: #0754C4;
      font-size: 18px;
      font-weight: 600;
      line-height: 16px;
      width: 521px;
      height: 10px;
      text-align: left;
    }

    .tamanoiconodropdown {
      width:35px; 
      height:32px;
  }

   }

   @media screen and (max-width: 330px) {
     .subtitulo {
       font-size: 14.5px;
     }

    .lista {
      color: #6F6F6F;
      font-size: 14px;
      font-weight: 500;
      line-height: 18px;
      width: 275px;
      text-align: left;
    }

    .lista2 {
      color: #0754C4;
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
      width: 300px;
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
