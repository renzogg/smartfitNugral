# smartfitNugral
Panel de administracion de nugral para smart fit

dni: id de identificar //entrada
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
    },
      {
      "id": 1,
      "name": "caminata (correr/Trotadora/Eliptica)",
      "frecuent": "Frecuencia x semana: 4 dias/ duracion"
    }
  ]
}
alimentacion : registra tus alimentos mas frecuentes -->  traer la lista de alimentos// incluir micro y macro por alimentos? //salida
         {
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
/*
registro(dni,edad,genere,meta,biotipo,grasa,actividad_fisica,alimentacion)
*/
/*registro("46400674",30,0,1,2,25,objeto_actividad,objeto_alimentacion)*/


 modelo referencial de entrada
{
  "params": {
    "dni": "12345678",
    "age": 30,
    "genere": 0,
    "meta": 1,
    "biotipo": 2,
    "grasa": 25,
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
relacion_cc: relacion cintura cadera 
gasto_kcal: gasto en calorias kcal tiempo promedio??
alimentacion: resultado de acuerdo a las calorias kcal
analisis_alimentos: carbohidratos, proteinas, grasas, fibra 
objetivo: reduccion mensual deseada % y kg y semanas estimadas para alcanzar objetivos

modelar result api

*----------------------------------------------------------------------------------------------------*
insertar otro estado **
 actualizar_mediciones(peso,imc,grasa,relacion_cc)-->resultado_actualizado
 actualizar_actividad_fisica(actvidad_fisica)-->resultado_actualizado
actualizar_alimentacion(alimentacion)-->resultado_actualizado

registro_diario()

/* panel de administracion*/
    login
    recuperar_contraseña
    administrador_de_contenidos
    

/* fin de panel de administracion*/