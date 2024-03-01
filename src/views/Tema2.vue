<template lang="pug">
.curso-main-container.pb-3
  BannerInterno
  .container.tarjeta.tarjeta--blanca.p-4.p-md-5.mb-5
    .titulo-principal.color-acento-contenido
      .titulo-principal__numero
        span 2
      h1 SQL para la creación y eliminación de bases de datos - DDL

    .row.justify-content-center.align-items-center.bg11.px-3.py-4.mb-5(data-aos="fade-left")
      .col-lg-12
        .row.justify-content-center.align-items-center.bg10
          .col-lg-auto.col-md-12
            img(data-aos="zoom-in")(src='@/assets/curso/temas/4.png', style="max-width: 296px").mx-auto  
          .col-lg(data-aos="fade-down") 
            p(data-aos="fade-down").pt-md-3.pt-lg-0 Cada grupo de entidades que tienen un modelo completo, forma una base de datos. Desde la perspectiva de SQL, una base de datos es únicamente un conjunto de relaciones (o tablas) y para organizarlas o diferenciarlas, se accede a ellas por su nombre. A nivel de sistema operativo, cada base de datos se almacena en un directorio distinto por MySQL. Por este motivo, crear una base de datos es un trabajo muy sencillo, claro que, a la hora de crearla, la base de datos estará desocupada, es decir, no almacenará ninguna tabla. 


    .cajon-b.color-blue-ligth.p-3.mb-5
      p.mb-0 #[b Es fundamental que mientras se estudia,] se ejecuten las sentencias propuestas aquí de esa manera se consolidarán los conocimientos de cada tema tratado. Se debe tomar el tiempo necesario para escribir en la consola cada una de las sentencias, es un ejercicio fundamental para asimilar el conocimiento que se está adquiriendo. 

    p.mb-5 De la misma forma, se deben revisar los resultados que le da la ejecución, en caso de algún error en la sintaxis, la respuesta dará una idea de qué puede estar fallando. #[b Ahora, se va  a crear y manejar una base de datos de práctica, a la vez que se familiarice con la manera de trabajar de MySQL]. 

    .row.justify-content-center.mb-5
      .col-xl-8
        .bg-color-acento-contenido.p-4.border-radius-default.mb-4(data-aos="fade-left")
          .row 
            .col-auto
              img(src='@/assets/curso/temas/icon1.svg', alt='', style="max-width: 72px")
            .col
              p.mb-0 Para iniciar, se creará una base de datos únicamente para practicar, y se llamará #[strong “prueba”]: 



    .bg-img-1.bg-full.mb-5(data-aos="zoom-in")
      .bg-container-full
        .tarjeta.tarjeta--bgSlyde.p-4(data-aos="fade-left")
          SlyderA(tipo="b")
            .row.justify-content-center.align-items-center.p-2
              .col-lg-5.col-md-auto
                p Se usa la sentencia #[b.text-color-acento-contenido CREATE DATABASE] para crear una base de datos:                  
              .col-lg-5.mb-4.mb-md-0
                img.img-a.img-t(src='@/assets/curso/temas/2-1.png') 

            .row.justify-content-center.align-items-center.p-2
              .col-lg-5.col-md-auto
                p Se puede saber cuántas bases de datos se encuentran en nuestro sistema usando la sentencia #[b.text-color-acento-contenido SHOW DATABASES]:                  
              .col-lg-5.mb-4.mb-md-0
                img.img-a.img-t(src='@/assets/curso/temas/2-2.png') 

            .row.justify-content-center.align-items-center.p-2
              .col-lg-5.col-md-auto
                p Desde ahora, en los siguientes puntos, se trabajará con la base de datos creada, por lo cual, la elegirá como base de datos por defecto. Esto nos evitará poner el nombre de la base de datos en consultas. Para escoger una base de datos se emplea el comando #[b.text-color-acento-contenido USE], que no es puntualmente una sentencia SQL, sino una opción de #[b.text-color-acento-contenido MySQL]:                   
              .col-lg-5.mb-4.mb-md-0
                img.img-a.img-t(src='@/assets/curso/temas/2-3.png') 

            .row.justify-content-center.align-items-center.p-2
              .col-lg-5.col-md-auto
                p Para borrar una base de datos, se usa la sentencia #[b.text-color-acento-contenido SQL DROP]. A continuación, se borrará la base de datos prueba, listaremos las existentes y la volveremos a crear:         
              .col-lg-5.mb-4.mb-md-0
                img.img-a.img-t(src='@/assets/curso/temas/2-4.png') 


            .row.justify-content-center.align-items-center.p-2
              .col-lg-5.col-md-auto
                p Liste las bases de datos para comprobar que ya no existe la base de datos antes creada.      
              .col-lg-5.mb-4.mb-md-0
                img.img-a.img-t(src='@/assets/curso/temas/2-5.png') 


    Separador

    #t_2_1.titulo-segundo.color-acento-contenido(data-aos='fade-right')
      h2 2.1 SQL para la creación y eliminación de tablas 


    .row.justify-content-center.talign-items-center
      .col-xl-6
        p A continuación, la sentencia #[strong #[em CREATE TABLE]] que se empleará para la creación de tablas. Esta sentencia tiene una sintaxis algo compleja, debido a que existen muchas opciones y se tienen varias posibilidades diferentes cuando se desea crear una tabla. 

        .row
          .col-lg-8.col
            a.anexo.bg-color-acento-botones.mb-4(:href="obtenerLink('/downloads/prueba.pdf')" target="_blank")
              .anexo__icono
                img(src="@/assets/template/icono-pdf.svg")
              .anexo__texto
                p Anexo. Para ampliar la información, lo invitamos a ver el PDF #[strong #[em “CREATE TABLE”]]. 

      
      .col-xl-6
        figure
          img.img-a.img-t(src='@/assets/curso/temas/5.png') 


    Separador
    
    #t_2_2.titulo-segundo.color-acento-contenido(data-aos='fade-right')
      h2 2.2 Claves foráneas

    p En MySQL únicamente existe soporte para claves foráneas en tablas de tipo #[strong InnoDB].  
    p.mb-5  #[strong InnoDB] es el motor de almacenamiento por defecto de las últimas versiones de MySQL, no obstante, esto no imposibilita usarlas en otros tipos de tablas.
    

    .row.mb-4.align-items-center
      .col-xl-5

        .bg-color-acento-contenido.p-4.border-radius-default.mb-4(data-aos="fade-left")
          .row 
            .col-auto
              img(src='@/assets/curso/temas/icon1.svg', alt='', style="max-width: 72px")
            .col
              p.mb-0 Primero se crea la tabla persona:  


        figure.mt-5
          img(src='@/assets/curso/temas/6.png')

      .col-xl-7 
        p Si se quiere crear una base de datos que corresponda al modelo que se está presentando anteriormente, las sentencias para la tabla teléfonos con la referencia a la tabla, sería: 

        figure.mt-5
          img(src='@/assets/curso/temas/7.png')

    p Se ha usado una definición a modo referencia para la columna “numero” de la tabla 'telefonos', señalando que es una clave foránea oportuna a la columna 'id_persona' de la tabla 'persona' a través de la columna persona_id. No obstante, aunque la sintaxis, se evidencia. 

    .row.mb-4.align-items-center
      .col-xl-5

        p La expresión #[strong #[em DELETE CASCADE]], hace que, si se borra una fila de la tabla persona que tiene relacionados registros telefónicos a través de la columna persona_id en la tabla telefonos, estos registros (localizados en la tabla telefonos) se borren si se borra el de la tabla persona; a este tipo de condiciones se le llama restricción de integridad referencial.


        p De igual forma #[strong #[em UPDATE CASCADE]], hace que, si el id_persona en una fila de la tabla persona es actualizado a otro valor y existen referencias en la columna persona_id de la tabla telefonos con el valor inicial, al cambiar el valor en el registro id_persona, cambien también el valor en los registros en la columna persona_id de la tabla telefonos. A este tipo de condiciones también se le llama restricción de integridad referencial. 

        p #[strong Y ejecutándola en la consola, el resultado sería: ]



      .col-xl-7 

        figure.mt-5
          img(src='@/assets/curso/temas/8.png')


    .row.justify-content-center
      .col-xl-10
        div(style="background-color: #BAE9D9").p-4.mb-4
          p Miremos otra variante de la misma sintaxis definiendo explícitamente que se usará el motor #[strong InnoDB] para que las reglas de restricción de integridad apliquen: 


</template>

<script>
export default {
  name: 'Tema2',
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
