<template lang="pug">
    div 
        div.moverizquierda
          b-breadcrumb-item(:to="regresarPrincipal")
            img.w-1(src="@/static/media/icons/PathCopy3.png")
            span.omnes-medium.linkprincipal Principal
          span
            span.omnes-medium(style="padding-right:6px;") ›
            span.omnes-semibold(style="color: #0754C4; font-size: 13px;") {{nombrepagina}}

        div.pd-top-bot(style="padding-top:8px;")
                h5.omnes-medium.titulopf.ocultar-div(style="padding-bottom:15px") {{nombrepagina}}
                div.centrar
                    div.ocultar.centrar.rectangulo(style="margin-bottom:20px; margin-top:0px")
                        <b-dropdown class="m-2" menu-class="w-100" style="width:100%;" variant="white" toggle-class="text-decoration-none" no-caret>
                            <template v-slot:button-content>       
                                div.izquierdadesplegable   
                                    div(style="display: flex; align-items: center;")
                                        img.tamanoiconodropdown(:src="imagenMenu" style="width:2rem; float:left;")
                                        div.titulo_dropdown.omnes-medium(style="white-space: break-spaces;") {{nombrepagina}}
                                    div
                                        img.tamanoflechadropdown(src="@/static/media/icons/arrow_down.png" style="width:15px; height:auto;")
                            </template> 
                                b-dropdown-item.opcionesdropdown.omnes-medium(:to="item.to" v-for="(item, index) in itemsMenu" :key="index") {{item.title}}
                        </b-dropdown>
                div.linea
                div(v-for="(item, index) in preguntas" :key="index")             
                    div.centrarpregunta(v-b-toggle="item.identificador" style="height:64px;") 
                        div.lista2pf.omnes-semibold.when-opened.acomodarlista {{item.title}} 
                        div.listapf.omnes-medium.when-closed.acomodarlista {{item.title}} 
                        img.when-opened.flechapf.tamanoflecha2(src="@/static/media/icons/arrow_up.png")
                        img.when-closed.flechapf.tamanoflecha2(src="@/static/media/icons/arrow_down.png")
                    b-collapse(:id="item.identificador" accordion="accordion")
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
    regresarPrincipal: String,
    imagenMenu: String,
    nombrepagina: String,
  },
  data() {
    return {
      
    };
  },

  methods: {
   
  }

};
</script>

<style scoped lang="scss">

      ::v-deep .dropdown-item {
        word-wrap: break-word !important;
        white-space: break-spaces !important; 
        line-height: 20px;
      }

    .titulo_dropdown {
      width: 100%; 
      height: auto; 
      word-wrap: break-word; 
      padding-left:10px; 
      padding-right:20px; 
      color: #0754C4; 
      font-size: 1.5rem; 
      font-weight: 600;
      text-align: left; 
      line-height: 25px;
    }

    .breadcrumb-item {
      display: inline-block;
    }

    .collapsed > .when-opened,
    :not(.collapsed) > .when-closed {
        display: none;
    }

    .pd-top-bot {
      padding: 14px 0;
    }

    .linkprincipal {
      padding-left:5px;
      padding-right:6px;
      padding-bottom:7px;
      padding-top:7px; 
      font-size: 14px;
      color:#9A9AA3;
    }

    .centrarpregunta {
       display: flex;
       align-items: center;
       justify-content: space-between;
     }

     .centrarpregunta:focus {
       outline: none;
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

    .tamanoflechadropdown {
      width:15px; 
      height:8px;
    }

 

  .flechapf {
    position: relative;
    left: -90px;
  }

  #banner-links .links-text:hover {
    text-decoration: none;
  }

.titulopf {
  color: #0754C4;
  font-size: 30px;
  font-weight: 600;
  line-height: 30px;
  text-align: left;
  padding-top: 15px;
}

.linea {
  background-color:#D8D8D8;
  width: 653px;
  height: 2px;
}

.estiloparrafo {
  color: #6f6f6f;
  font-size: 1rem;
  font-weight: 400;
  line-height: 30px;
  text-align: left;
  padding-top: 0px;
}

.listapf {
  color: #6F6F6F;
  font-size: 1.1rem;
  font-weight: 500;
  line-height: 24px;
  width: 550px;
  text-align: left;
}

.lista2pf {
  color: #0754C4;
  font-size: 1.1rem;
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
    width: 96%;
  }

  .parrafo {
    color: #6f6f6f;
    font-size: 1rem;
    font-weight: 400;
    line-height: 30px;
    width: 87%;
    text-align: left;
    padding-top: 0px;
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

    .flechapf {
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
      font-size: 1rem;
      font-weight: 400;
      line-height: 30px;
      width: 96%;
      text-align: left;
      padding-top: 0px;
    }
  

   }

   @media screen and (min-width: 1200px) {
     .ocultar {
       display: none;
     }

   }

   @media screen and (max-width: 991px) {


    .parrafo {
      color: #6f6f6f;
      font-size: 1rem;
      font-weight: 400;
      line-height: 30px;
      // width: 96%;
      text-align: left;
      padding-top: 0px;
    }

    .listapf {
      color: #6F6F6F;
      font-size: 1.1rem;
      font-weight: 500;
      line-height: 24px;
      width: 409px;
      text-align: left;
    }

    .lista2pf {
      color: #0754C4;
      font-size: 1.1rem;
      font-weight: 500;
      line-height: 24px;
      width: 409px;
      text-align: left;
    }

    .parrafo {
      color: #6f6f6f;
      font-size: 1rem;
      font-weight: 400;
      line-height: 30px;
      // width: 435px;
      text-align: left;
      padding-top: 0px;
    }
    

  .achicarpf {
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
      font-size: 1rem;
      font-weight: 400;
      line-height: 30px;
      // width: 525px;
      text-align: left;
      padding-top: 0px;
      padding-left: 20px;
    }
    


    .estiloparrafo {
      color: #6f6f6f;
      font-size: 1rem;
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
      width: 96%;
    }

    


   }

   @media screen and (max-width: 540px) {

     .titulo_dropdown {
        width: 100%; 
        height: auto; 
        word-wrap: break-word; 
        padding-left:10px; 
        padding-right:20px; 
        color: #0754C4; 
        font-size: 1.2rem; 
        font-weight: 600;
        text-align: left;
        line-height: 20px; 
      }

    .listapf {
      color: #6F6F6F;
      font-size: 1rem;
      font-weight: 500;
      line-height: 20px;
      width: 400px;
      text-align: left;
    }

    .lista2pf {
      color: #0754C4;
      font-size: 1rem;
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

    .reducirespaciadosection {
      margin-top: 18px;
    }

     .parrafo {
      color: #6f6f6f;
      font-size: 1rem;
      font-weight: 400;
      line-height: 26px;
      // width: 500px;
      text-align: left;
      padding-top: 0px;
      padding-left: 20px;
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
      font-size: 0.9rem;
      font-weight: 400;
      line-height: 26px;
      // width: 460px;
      text-align: left;
      padding-top: 0px;
      padding-left: 20px;
    }

    .tamanoiconodropdown {
      width:40px; 
      height:auto;
  } 

   }

    @media screen and (max-width: 490px) {

    .parrafo {
      color: #6f6f6f;
      font-size: 0.9rem;
      font-weight: 400;
      line-height: 24px;
      // width: 440px;
      text-align: left;
      padding-top: 0px;
      padding-left: 20px;
    }
  
     
   }

   @media screen and (max-width: 469px) {

    
    .titulo_dropdown {
        width: 100%; 
        height: auto; 
        word-wrap: break-word; 
        padding-left:10px; 
        padding-right:20px; 
        color: #0754C4; 
        font-size: 1.1rem; 
        font-weight: 600;
        text-align: left;
        line-height: 20px; 
    }

    .tamanoflecha2 {
      width: 26px;
      height: 6px;
    }

    .listapf {
      color: #6F6F6F;
      font-size: 0.9rem;
      font-weight: 500;
      line-height: 18px;
      width: 380px;
      text-align: left;
    }

    .lista2pf {
      color: #0754C4;
      font-size: 0.9rem;
      font-weight: 500;
      line-height: 18px;
      width: 380px;
      text-align: left;
    }

    .parrafo {
      color: #6f6f6f;
      font-size: 0.9rem;
      font-weight: 400;
      line-height: 24px;
      // width: 420px;
      text-align: left;
      padding-top: 0px;
      padding-left: 20px;
    }
    

   }


   @media screen and (max-width: 455px) {

    .listapf {
      color: #6F6F6F;
      font-size: 0.9rem;
      font-weight: 500;
      line-height: 18px;
      width: 360px;
      text-align: left;
    }

    .lista2pf {
      color: #0754C4;
      font-size: 0.9rem;
      font-weight: 500;
      line-height: 18px;
      width: 360px;
      text-align: left;
    }

    .parrafo {
      color: #6f6f6f;
      font-size: 0.9rem;
      font-weight: 400;
      line-height: 24px;
      // width: 405px;
      text-align: left;
      padding-top: 0px;
      padding-left: 20px;
    }

   }

   @media screen and (max-width: 440px) {

    .listapf {
      color: #6F6F6F;
      font-size: 0.9rem;
      font-weight: 500;
      line-height: 18px;
      width: 320px;
      text-align: left;
    }

    .lista2pf {
      color: #0754C4;
      font-size: 0.9rem;
      font-weight: 500;
      line-height: 18px;
      width: 320px;
      text-align: left;
    }

    .parrafo {
      color: #6f6f6f;
      font-size: 0.9rem;
      font-weight: 400;
      line-height: 24px;
      // width: 395px;
      text-align: left;
      padding-top: 0px;
      padding-left: 20px;
    }
  
   }

   @media screen and (max-width: 425px) {

    .listapf {
      color: #6F6F6F;
      font-size: 0.9rem;
      font-weight: 500;
      line-height: 18px;
      width: 330px;
      text-align: left;
    }

    .lista2pf {
      color: #0754C4;
      font-size: 0.9rem;
      font-weight: 500;
      line-height: 18px;
      width: 330px;
      text-align: left;
    }

    .parrafo {
      color: #6f6f6f;
      font-size: 0.9rem;
      font-weight: 400;
      line-height: 24px;
      // width: 390px;
      text-align: left;
      padding-top: 0px;
      padding-left: 20px;
    }

   }

   @media screen and (max-width: 400px) {

    .listapf {
      color: #6F6F6F;
      font-size: 0.9rem;
      font-weight: 500;
      line-height: 18px;
      width: 320px;
      text-align: left;
    }

    .lista2pf {
      color: #0754C4;
      font-size: 0.9rem;
      font-weight: 500;
      line-height: 18px;
      width: 320px;
      text-align: left;
    }

    .parrafo {
      color: #6f6f6f;
      font-size: 0.9rem;
      font-weight: 400;
      line-height: 24px;
      // width: 370px;
      text-align: left;
      padding-top: 0px;
      padding-left: 20px;
    }
   
   }

   @media screen and (max-width: 381px) {

     .titulo_dropdown {
        width: 100%; 
        height: auto; 
        word-wrap: break-word; 
        padding-left:10px; 
        padding-right:20px; 
        color: #0754C4; 
        font-size: 1.1rem; 
        font-weight: 600;
        text-align: left;
        line-height: 18px; 
    }

    .listapf {
      color: #6F6F6F;
      font-size: 0.9rem;
      font-weight: 500;
      line-height: 18px;
      width: 300px;
      text-align: left;
    }

    .lista2pf {
      color: #0754C4;
      font-size: 0.9rem;
      font-weight: 500;
      line-height: 18px;
      width: 300px;
      text-align: left;
    }

    .parrafo {
      color: #6f6f6f;
      font-size: 0.9rem;
      font-weight: 400;
      line-height: 24px;
      // width: 340px;
      text-align: left;
      padding-top: 0px;
      padding-left: 20px;
    }

   }

   @media screen and (max-width: 359px) {

     .listapf {
      color: #6F6F6F;
      font-size: 0.9rem;
      font-weight: 500;
      line-height: 18px;
      width: 290px;
      text-align: left;
    }

    .lista2pf {
      color: #0754C4;
      font-size: 0.9rem;
      font-weight: 500;
      line-height: 18px;
      width: 290px;
      text-align: left;
    }

    .parrafo {
      color: #6f6f6f;
      font-size: 0.9rem;
      font-weight: 400;
      line-height: 24px;
      // width: 320px;
      text-align: left;
      padding-top: 0px;
      padding-left: 20px;
    }


   }

   @media screen and (max-width: 349px) {


    .parrafo {
      color: #6f6f6f;
      font-size: 0.8rem;
      font-weight: 400;
      line-height: 24px;
      // width: 320px;
      text-align: left;
      padding-top: 0px;
      padding-left: 20px;
    }

   }

   @media screen and (max-width: 338px) {

    .parrafo {
      color: #6f6f6f;
      font-size: 0.8rem;
      font-weight: 400;
      line-height: 24px;
      // width: 310px;
      text-align: left;
      padding-top: 0px;
      padding-left: 20px;
    }

    .tamanoiconodropdown {
      width:35px; 
      height:auto;
  }

   }

   @media screen and (max-width: 330px) {

    .listapf {
      color: #6F6F6F;
      font-size: 0.9rem;
      font-weight: 500;
      line-height: 18px;
      width: 275px;
      text-align: left;
    }

    .lista2pf {
      color: #0754C4;
      font-size: 0.9rem;
      font-weight: 500;
      line-height: 18px;
      width: 275px;
      text-align: left;
    }

    .parrafo {
      color: #6f6f6f;
      font-size: 0.8rem;
      font-weight: 400;
      line-height: 24px;
      // width: 300px;
      text-align: left;
      padding-top: 0px;
      padding-left: 20px;
    }
    
   }
</style>
