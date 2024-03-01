<template lang="pug">
.curso-main-container.pb-3
  BannerInterno
  .container.tarjeta.tarjeta--blanca.p-4.p-md-5.mb-5
    .titulo-principal.color-acento-contenido
      .titulo-principal__numero
        span 1
      h1 Interface de línea de comandos de MySQL 
      
    .row.justify-content-center.align-items-center.bg11.px-3.py-4(data-aos="fade-left")
      .col-lg-12
        .row.justify-content-center.align-items-center.bg10
          .col-lg-auto.col-md-12
            img(data-aos="zoom-in")(src='@/assets/curso/temas/1.png', style="max-width: 287px").mx-auto  
          .col-lg(data-aos="fade-down") 
            p(data-aos="fade-down").pt-md-3.pt-lg-0 Al iniciar a trabajar con el SGBD, existen varias maneras de enlazar una comunicación con el servidor de MySQL. Generalmente en el software, se usará un API para hacer las consultas y otras operaciones con el servidor. Por ejemplo, en PHP, esta API está integrada con el lenguaje. 

            p(data-aos="fade-down") En este punto se usará MySQL de forma directa, por medio de un cliente ejecutándose desde una consola (una ventana de comandos en Windows). En otras secciones se explicarán las distintas APIs.   

    Separador

    #t_1_1.titulo-segundo.color-acento-contenido(data-aos='fade-right')
      h2 1.1 Aplicación cliente de MySQL 

    p(data-aos="fade-left") Primero, se deben seguir las siguientes instrucciones, para conectarse a la base de datos a través del cliente de línea de comandos: 

    .bg-img-1.bg-full.mb-5(data-aos="zoom-in")
      .bg-container-full
        .tarjeta.tarjeta--azul.p-4
          LineaTiempoC.color-acento-contenido(text-small)
            .row(titulo="Paso 1").align-items-center.justify-content-center
              .col-xl-10
                .row.align-items-center.justify-content-center
                  .col-md-6
                    p Debe abrir inicio y buscar MySQL o teclear "mysql" y se hace clic en “MySQL Command Line Client”. 
                
                  .col-md-6
                    figure
                      img(src='@/assets/curso/temas/paso1.png', alt='')


            .row(titulo="Paso 2").align-items-center.justify-content-center
              .col-xl-10
                .row.align-items-center.justify-content-center
                  .col-md-6
                    p Ingresa la contraseña de root usada en el proceso de instalación de MySQL. 
                
                  .col-md-6
                    figure
                      img(src='@/assets/curso/temas/paso2.png', alt='')


            .row(titulo="Paso 3").align-items-center.justify-content-center
              .col-xl-10
                .row.align-items-center.justify-content-center
                  .col-md-6
                    p Una vez autenticado en la interface comando de línea, vemos este resultado.  
                
                  .col-md-6
                    figure
                      img(src='@/assets/curso/temas/paso3.png', alt='')

    .bg-img-2.bg-full.mb-5
      .bg-container-full
        .row.justify-content-center 
          .col-xl-8
            .bg-color-acento-contenido.p-4.border-radius-default.mb-4(data-aos="fade-left")
              .row 
                .col-auto
                  img(src='@/assets/curso/temas/icon1.svg', alt='', style="max-width: 72px")
                .col
                  p.mb-0 En adelante, los resultados de interface de línea de comandos se presentarán como se presenta a continuación:  

            figure.mb-4(data-aos="zoom-in")
              img(src='@/assets/curso/temas/figura1.svg', alt='')


            .bg-color-acento-contenido.p-4.border-radius-default.mb-4(data-aos="fade-left")
              p.mb-0 Y, para salir de la consola de comando, se usa el comando quit (en mayúscula o minúscula). 

            figure.mb-4(data-aos="zoom-in")
              img(src='@/assets/curso/temas/figura2.svg', alt='')


    .bg-img-2xs.bg-full.mb-5
      .bg-container-full

        #t_1_2.titulo-segundo.color-acento-contenido(data-aos='fade-right')
          h2 1.2 Prueba de consultas básicas

        p Ya se conoce cómo entrar y salir del cliente MySQL, y se tiene la posibilidad de realizar consultas, ahora, lo más fácil es consultar varias variables del sistema o el valor de varias funcionalidades de MySQL. Para realizar esta clase de consultas se utiliza la sentencia #[b SQL SELECT], por ejemplo: 

        .row.mb-5
          .col-xl-5
            figure.mb-4(data-aos="zoom-in")
              img(src='@/assets/curso/temas/figura3.svg', alt='')
          .col-xl-7
            p(data-aos="fade-left") #[b SELECT] es la sentencia SQL para elegir datos de bases de datos, además se puede utilizar, como en esta situación, para consultar cambiantes del sistema o resultados de funcionalidades. En este caso, se ha consultado el resultado de la función #[b VERSION], se sabe que es una función porque tiene paréntesis” ()”, y de la variable #[b CURRENT_DATE]. 

            .bg-color-acento-contenido.p-4.border-radius-default.mb-4(data-aos="fade-left")
              p.mb-0 Toda sentencia debe finalizar con punto y coma (;), luego debe dar #[b enter]. 

    Separador

    #t_1_3.titulo-segundo.color-acento-contenido(data-aos='fade-right')
      h2 1.3  SQL – #[em Standard Query Language]

    .bg-img-2.bg-full.mb-5
      .bg-container-full

        p(data-aos='fade-right') En el nivel teórico, existen dos lenguajes para el uso de bases de datos: 

        .row.justify-content-center.mb-5
          .col-lg-6.mb-lg-0.mb-3(data-aos='fade-right')
            .p-5.h-100.card2(style="background-color: #273A89")
              img(src='@/assets/curso/temas/icon2.svg', alt='' style="width: 73px").mb-4
              .titulo-card.d-inline-block(style="background-color: #3EE2A8").p-1.px-3.mb-3
                h4.d-inline-block.mb-0 DDL #[em (Data Definition Language)].
              p.text-white Es el lenguaje que se emplea para establecer bases de datos y tablas, y para transformar sus estructuras. Este lenguaje trabaja sobre ciertas tablas especiales llamadas diccionario de datos.
          .col-lg-6.mb-lg-0.mb-3(data-aos='fade-left')
            .p-5.h-100.card2(style="background-color: #273A89")
              img(src='@/assets/curso/temas/icon2.svg', alt='' style="width: 73px").mb-4
              .titulo-card.d-inline-block(style="background-color: #3EE2A8").p-1.px-3.mb-3
                h4.d-inline-block.mb-0 DML #[em (Data Manipilation Language)]. 
              p.text-white Es lo que se usa para cambiar y obtener datos desde las bases de datos.

        .row.justify-content-center.align-items-center.mb-5
          .col-lg-5
            .p-4(data-aos='fade-right')
              img(src='@/assets/curso/temas/3.svg', alt='' style="max-width: 505px").mb-4.mx-auto

          .col-lg-7(data-aos='fade-left')
            p #[b SQL abarca ambos lenguajes:]

            .bg-color-acento-botones.border-radius-defult.my-4(style="width: 200px")
              .p-2
                h5.text-center.mb-0 DDL + DML

            p En este punto se explicará el proceso para convertir del modelo lógico relacional, al modelo físico, empleando sentencias SQL. Ya no se empleará (por ahora), MySQL Workbeach, y se observarán las particularidades específicas de MySQL. 
              
</template>

<script>
export default {
  name: 'Tema1',
  components: {},
  data: () => ({
    // variables de vue
  }),
  mounted() {
    this.$nextTick(() => {
      this.$aosRefresh()
    })
  },
  updated() {
    this.$aosRefresh()
  },
}
</script>

<style lang="sass"></style>
