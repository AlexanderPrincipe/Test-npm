<template lang="pug">
  #text-links
    div(v-for="(item, index) in links")
      router-link.omnes-medium(:to="item.to" target="_self" class="links-text")
        div.centrarLink(style="height:44px;")
          img(:src="item.imagen")
          span.dudas-frecuentes {{item.title}}

</template>

<script>
export default {
  name: 'TextLinksRenovadoGenerico',
  props: {
    links: {
      type: Array,
    },
    
  },
  data () {
    return { 
        
    }
  }
}
</script>

<style >
  #text-links div {
    margin-bottom: 20px;
  }
  #text-links img, #text-links span {
    filter: contrast(0%)
  }
  #text-links img {
    width: 2.8rem;
    padding-right: 14px;
  }
  #text-links a:hover {
    text-decoration: none;
  }
  #text-links .nuxt-link-exact-active span,
  #text-links .nuxt-link-exact-active img {
    color: #0754C4 !important;
    font-family: 'Omnes Semibold';
    filter: contrast(100%)
  }

  .dudas-frecuentes {
    color: #6F6F6F;
    font-size: 18px;
    font-weight: 400;
    line-height: 16px;
    text-align: left;
  }

  .centrarLink {
       display: flex;
       justify-content: flex-start;
       align-items: center;
  }
</style>
