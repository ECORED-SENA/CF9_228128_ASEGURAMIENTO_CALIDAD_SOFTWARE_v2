<template lang="pug">
.curso-main-container.pb-3
  BannerInterno
  .container.tarjeta.tarjeta--blanca.p-4.p-md-5.mb-5
    .titulo-principal.color-acento-contenido
      .titulo-principal__numero
        span 3
      h1 SQL para la manipulación de datos - DML 
    p.mb-5(data-aos='fade-right') Una base de datos sin datos no es muy útil, de manera que se verá cómo añadir, modificar o eliminar los datos que poseen las bases de datos.
        br
        br
        |#[b A continuación, se creará una tabla con la que seguiremos ejemplificando la sintaxis del SQL:]  
    .row.justify-content-center.mb-5
      .col-lg-7.col-10.mb-lg-0.mb-3: img(src='@/assets/curso/temas/9.png', alt='')
      .col-lg-5.col-6: img(src='@/assets/curso/temas/10.svg', alt='')
    Separador 
    #t_3_1.titulo-segundo.color-acento-contenido(data-aos='fade-right')
      h2 3.1 Inserción de registros 
    p.mb-5(data-aos='fade-right') La forma más directa de implantar una fila nueva en una tabla es por medio de una sentenci INSERT. 
    .bg-img-1.bg-full.mb-5(data-aos="zoom-in")
      .bg-container-full
        .tarjeta.tarjeta--bgSlyde.p-4(data-aos="fade-left")
          SlyderA(tipo="b")
            .row.justify-content-center.align-items-center.p-2
              .col-lg-5.col-md-auto
                p De la manera más sencilla, en esta sentencia se debe indicar la tabla a la que se quiere agregar filas, y los valores de cada columna. Las columnas de tipo cadena o fechas tienen que estar entre comillas sencillas o dobles,  esto no es obligatorio para las columnas numéricas, aunque también pueden estar entrecomilladas.                 
              .col-lg-5.mb-4.mb-md-0
                a.lnk(@click="modal1 = true")
                  img.img-a.img-t(src='@/assets/curso/temas/11.svg') 
            .row.justify-content-center.align-items-center.p-2
              .col-lg-5.col-md-auto
                p.text-white  Si no se requiere determinar un valor preciso para alguna columna, se puede determinar el valor por defecto indicado para esa columna cuando la tabla fue creada, usando la palabra #[b.text-color-acento-contenido #[em DEFAULT:]]                
              .col-lg-5.mb-4.mb-md-0
                img(src='@/assets/curso/temas/13.png', alt='')
            .row.justify-content-center.align-items-center.p-2
              .col-lg-5.col-md-auto
                p.text-white  Mire como Perillo tiene el valor por defecto definido en la columna fecha y edad.                
              .col-lg-5.mb-4.mb-md-0
                img(src='@/assets/curso/temas/14.png', alt='')
            .row.justify-content-center.align-items-center.p-2
              .col-lg-5.col-md-auto
                p.text-white   El orden en la sentencia #[b.text-color-acento-contenido #[em INSERT]] es muy importante, que conserve una correspondencia. 
                  br
                  br
                  |Finalmente, estamos listos para aprender cómo se actualizan los datos que se han registrado.               
              .col-lg-5.mb-4.mb-md-0
                img(src='@/assets/curso/temas/15.png', alt='')
    
    ModalA(:abrir-modal.sync="modal1")
      img(src='@/assets/curso/temas/12.png', alt='')
    Separador
    #t_3_2.titulo-segundo.color-acento-contenido(data-aos='fade-right')
      h2 3.2 Edición de registros
    p.mb-5(data-aos='fade-right') Tenemos la posibilidad de cambiar valores de las filas de una tabla utilizando la sentencia #[b #[em  UPDATE]]. En su manera más fácil, los cambios se usan a cada una de las filas, y a las columnas que se les especifique (MySQL 8.0 Reference Manual, 2021). 
    p.mb-5(data-aos='fade-right') Tenemos la posibilidad de cambiar valores de las filas de una tabla utilizando la sentencia #[b #[em UPDATE.]] En su manera más fácil, los cambios se usan a cada una de las filas, y a las columnas que se les especifique (MySQL 8.0 Reference Manual, 2021). 
    .row.justify-content-center.mb-5
      .col-lg-5.col-12.mb-lg-0.mb-3: img(src='@/assets/curso/temas/16.png', alt='')
      .col-lg-5.col-7: img(src='@/assets/curso/temas/17.png', alt='')
    p.mb-5(data-aos='fade-right').fw-bold Estudiemos el siguiente ejemplo:
    .bg-img-1.bg-full.mb-5(data-aos="zoom-in")
      .bg-container-full
        .tarjeta.tarjeta--azul.p-4
          LineaTiempoC.color-acento-contenido(text-small)
            .row(titulo="Paso 1").align-items-center.justify-content-center
              .col-xl-10
                .row.align-items-center.justify-content-center
                  .col-md-6
                    p Que todas las personas de la tabla gente tengan la misma fecha utilizando esta sentencia #[b.text-color-acento-contenido #[em UPDATE: ]]
                
                  .col-md-6
                    figure
                      img(src='@/assets/curso/temas/18.png', alt='')
            .row(titulo="Paso 2").align-items-center.justify-content-center
              .col-xl-10
                .row.align-items-center.justify-content-center
                  .col-md-6
                    p Al suponer que se necesita ponerle el incrementar la edad por 10 años a cada fila de la tabla gente: 
                
                  .col-md-6
                    figure
                      img(src='@/assets/curso/temas/19.png', alt='')
            .row(titulo="Paso 3").align-items-center.justify-content-center
              .col-xl-10
                .row.align-items-center.justify-content-center
                  .col-md-6
                    p Sin embargo no se tienen que actualizar todas filas de la tabla, ya que se tiene la posibilidad de definir cuáles filas se desean actualizar. 
                      br
                      br
                      |La primera es por medio de la cláusula #[b.text-color-acento-contenido #[em WHERE]]. Utilizando esta cláusula se tiene la posibilidad de entablar una condición. Únicamente las filas que cumplan dicha condición van a ser actualizadas: 
                
                  .col-md-6
                    figure
                      img(src='@/assets/curso/temas/20.png', alt='')
    p.mb-5.fw-bold(data-aos='fade-right') Otro ejemplo sería que se actualice la fecha al día 2012-12-12 para todos lo que sean mayores de 40 años de edad; esto se podría hacer así: 
    .row.justify-content-center.mb-5
      .col-lg-8.col-10: img(src='@/assets/curso/temas/21.png', alt='')
    Separador
    #t_3_3.titulo-segundo.color-acento-contenido(data-aos='fade-right')
      h2 3.3 Borrado de registros 
    .fondo-t3.mn.p-5
      p.mb-5(data-aos='fade-right') Para borrar filas se utiliza la sentencia #[em #[b DELETE.]] La sintaxis es muy similar a la de #[em #[b UPDATE:]] 
      .row.justify-content-center.mb-5
        .col-lg-6.col-8: img(src='@/assets/curso/temas/22.png', alt='')
      p.mb-5(data-aos='fade-right') Para borrar el registro que tiene por nombre Perillo se procede de la siguiente forma: 
      .row.justify-content-center.mb-5
        .col-lg-6.col-8: img(src='@/assets/curso/temas/23.png', alt='')
      p.mb-5(data-aos='fade-right') A continuación, se debe borrar aquello que tenga edad comprendida entre 30 (incluyendo 30) y 50 años (incluyendo 50), para eso se usa un operador llamado #[em #[b AND]], se verán con más detalle estos operadores. 
      .row.justify-content-center.mb-5
        .col-lg-6.col-8
          img(src='@/assets/curso/temas/24.png', alt='').mb-2
          figcaption  Nota. Tomado de MySQL 8.0 Reference Manual (2021). 
      .tarjeta.color-acento-contenido.p-2.d-inline-block.rounded-3.mb-4.icono-tres
        h5.mb-0 Vaciar una tabla
      p.mb-5(data-aos='fade-right') Cuando se deseen borrar todas las filas de una tabla, se puede utilizar una sentencia #[em #[b DELETE]] sin condiciones, como se vio en el punto anterior. Pero existe una sentencia alternativa, #[em #[b TRUNCATE]], que hace la misma tarea de una forma mucho más veloz. La diferencia es que #[em #[b DELETE]] hace un borrado secuencial de la tabla, fila por fila y  #[em #[b TRUNCATE]] elimina la tabla y la vuelve a crear desocupada, lo que es mucho más eficaz. 
      .row.justify-content-center.mb-5
        .col-lg-6.col-8.mb-lg-0.mb-3: img(src='@/assets/curso/temas/25.png', alt='')
        .col-lg-6.col-8: img(src='@/assets/curso/temas/26.svg', alt='')

</template>

<script>
export default {
  name: 'Tema3',
  data: () => ({
    mostrarIndicador: true,
    modal1: false,
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
