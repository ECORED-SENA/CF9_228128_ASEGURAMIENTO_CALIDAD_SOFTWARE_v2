<template lang="pug">
.curso-main-container.introduccion
  BannerInterno
  .container.tarjeta.tarjeta--blanca.p-4.p-md-5.mb-5
  
    .titulo-principal.color-acento-contenido
      .titulo-principal__numero
        span
          i.fas.fa-info
      h1 Introducción



    .cont_intro1.mb-5
      .row
        .col-xl-10.m-auto.mt-4
          .cont_intro2
            div.d-none.d-lg-block(style="width:100%;bottom:10%;top:5%;position:absolute;right:-4%;")
              figure
                img(src="@/assets/curso/intro/intro4.png")
            .row.p-5.pt-4.pb-4.p-lg-0
              .col-lg-auto.col-md-5.col-7.m-auto(style="place-self:center;" data-aos="fade-right")
                figure.mb-2.mt-4.mb-lg-0
                  img(src="@/assets/curso/intro/3.png")
              .col-lg.col-md-12.col-12.p-0.p-lg-4(style="place-self:center;" data-aos="fade-left")
                p.mb-0.pt-4 #[span.etiqueta Las siglas SQL, vienen del inglés Structured Query Language], es un lenguaje estándar que permite manipular los datos de una base de datos relacional. Casi todos los Sistemas de Gestión de Bases de Datos Relacionales (SGBD) implementan este lenguaje y mediante él se realiza todo tipo de actividad en la base de datos. En este componente formativo, se hace una presentación del lenguaje SQL, enfocándose en las sentencias de consulta de datos, empleando la interfaz de consola de línea de comandos, con el fin de fortalecer las técnicas de administración remota. Finalmente, se presentará la interfaz de administración gráfica para hacer las mismas operaciones. 

  </template>

<script>
export default {
  name: 'Introduccion',
  data: () => ({
    // variables de vue
  }),
}
</script>

<style lang="sass">
.cont_intro1, .cont_intro1 *
 position: relative
.cont_intro1:before
  position: absolute
  content: ''
  width: 125%
  left: -15%
  height: 100%
  top: auto
  bottom: auto
  background: rgb(220,236,254)
  background: linear-gradient(0deg, rgba(220,236,254,0) 0%, rgba(220,236,254,1) 25%, rgba(220,236,254,1) 75%, rgba(220,236,254,0) 100%)
.cont_intro2, .cont_intro2 *
 position: relative
.cont_intro2:before
  position: absolute
  content: ''
  width: 100%
  right: -4%
  top: 5%
  bottom: 10%
  height: 300px
  background-color: #ADD3FD
  border-radius: 17px
@media screen and (max-width: 992px)
  .cont_intro2:before
    width: 100%
    height: 100%
    right: 0
    top: 0
    bottom: 0
</style>
