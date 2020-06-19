# smartfitNugral
Panel de administracion de nugral para smart fit
Registro de paciente

dni: id de identificar dni nacional o extrejeria //entrada **
age: edad del id //entrada
genere: genero hombre o mujer //0:hombre o 1: mujer --> generar api // salida

meta: meta principal // peder peso, aumentar masa muscular, tonificar, mantenerme saludable -> generar como arrar de 0,1,2,3 lo cual se puede agregar a nivel de panel de adminstracion
         generar api para las metas // salida
measure: medidas corporales // {talla,peso,cintura,cadera,peso_objetivo} -- talla cm, peso kg, cintura cm (opcional), cadera cm (opcional), peso_objetivo kg // objeto //entrada

biotipo: seleccione su biotipo // ectomorfo mesomorfo endomorfo //0,1,2 como array
        generar api para biotipos //salida
grasa: porcentaje aproximado de grasa como numero 20%->20 25%->25 ... 45%->45 generar api //salida 

actividad_fisica: registra rutina promedio semanal // actividades --> traer api de actividades // salida
    {
  "actividad_fisica": [
    {
      "id": 0,
      "name": "cardio (correr/Trotadora/Eliptica)",
      "frecuent": "Frecuencia x semana: 2 dias/ duracion"
         frecuencia y  duracion: 2, 30min
    },
      {
      "id": 1,
      "name": "caminata (correr/Trotadora/Eliptica)",
      "frecuent": "Frecuencia x semana: 4 dias/ duracion"
          frecuencia y  duracion: 2, 30min
    }
  ]
}
/*base de datos en nugral de actividad fisica*/
alimentacion : registra tus alimentos mas frecuentes -->  traer la lista de alimentos// incluir micro y macro por alimentos? //salida
* solo por dia
         {
  "alimentos": [
    {
      "id": 0,
      "id_turno": "turno" desayuno media mañana almuerzo media tarde cena 0,1,2,3,4
      "name": "Jugo de alimentos",
      "frecuent": "Frecuencia x semana 3 días",<no va>
      cantidad:number 5 *
      "unidad":unidad por alimento
    },
    {
      "id": 1,
      "id_turno": "turno" desayuno media mañana almuerzo media tarde cena 0,1,2,3,4
      "name": "Pan integral",
           cantidad:number 5 *
      "frecuent": "Frecuencia x semana 5 días" <no va>
       "unidad":unidad por alimento,
    }
  ]
}
/*
registro(dni,edad,peso,altura,cc,genere,meta,biotipo,grasa,actividad_fisica,alimentacion)
*/
/*registro("46400674",30,0,1,2,25,objeto_actividad,objeto_alimentacion)*/


 modelo referencial de entrada
{
  "params": {
    "dni": "12345678",
    "age": 30,
    "genere": 0,
    "altura":165
    "cintura":*
    "cadera":*
    "meta": 1,
    "biotipo": 2,
    "grasa_actual": 25,opcional
    "grasa_deseado": 25,
    "actividad_fisica": [
      {
        "id": 0,
        "name": "cardio (correr/Trotadora/Eliptica)",
        "frecuent": "Frecuencia x semana: 2 dias/ duracion"
      },
      {
        "id": 1,
        "name": "caminata (correr/Trotadora/Eliptica)",
        "frecuent": "Frecuencia x semana: 4 dias/ duracion"
      }
    ],
    "alimentos": [
      {
        "id": 0,
        "name": "Jugo de alimentos",
        "frecuent": "Frecuencia x semana 3 días"
      },
      {
        "id": 1,
        "name": "Pan integral",
        "frecuent": "Frecuencia x semana 5 días"
      }
    ]
  }
}

//retorna

resultados optimos

peso:peso ideal // en kg
IMC: indice de masa  // kg
grasa: porcentaje en masa %
relacion_cc: relacion cintura cadera opcional si se conoce cadera-cintura
gasto_kcal: gasto en calorias kcal diarias--- tiempo promedio calorias quemadas por jercicio diarias en la semana semana
alimentacion: resultado de acuerdo a las calorias kcal//ingesta diaria      -semanal //solo cantidad 
recomendaciones: recomendaciones de acuerdo a los resultados anteriores
analisis_alimentos: carbohidratos, proteinas, grasas, fibra 
objetivo: reduccion mensual deseada % y kg y semanas estimadas para alcanzar objetivos

modelar result api


*----------------------------------------------------------------------------------------------------*
insertar otro estado ** por bloque mediciones/ejecicios/alimentos--> analisis de alimentos

/*variacion de  carbohidratos proteinas grasas  x biotipo distribucion porcentual * porcetuales por turnos*/
 actualizar_mediciones(peso,imc,grasa,relacion_cc)-->resultado_actualizado
 medicion afecta analisis de alimentos
 actualizar_actividad_fisica(actvidad_fisica)-->resultado_actualizado
actualizar_alimentacion(alimentacion)-->resultado_actualizado
reduccion mensual deseada--* traer
semanas estimadas---* traer
registro_semanal()


/* panel de administracion*/
    login
    recuperar_contraseña
    roles*
    analitica de datos*
    administrador_de_contenidos
     --> administracion de alimentos *por orden de preferencia
     --> administracion de actividades 
     --> administracion de metas* no se puede agregar mas
     --> administracion de clientes *
     --> administracion de dietas // recomendaciones
     --> % Grasa --> 31-35 es el promedio
     --> de biotipos * no va
     --> tips //consejos de acuerdo asu biotipo y % grasa // cuadro
     --> recomendaciones  //       ///recomendaciones por preferencia prioridad

/* fin de panel de administracion*/

/*aupiciadores*/
por busqueda de alimentos

/* historial de actualizacion*/
por 3 actualizacion anteriores regulares
y todos actulizaicoines premiun


api devolucion especialmente para el nutricionista de acuerdo al usuario