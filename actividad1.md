# ACTIVIDAD 1: 
>1. Instalar MongoDB en ambiente local. 
>2.  Conectarse a MongoDB vía CLI.
  >>     mongod
  >>     mongo
>3.  Crear una nueva base de datos llamada futbolfifa.
  >>    use futbolistas
  >>>   switched to db futbolistas
>4.  Crear una nueva collection llamada players.
  >>    db.createCollection("players")
  >>>   { "ok" : 1 }
>5.  Insertar 5 documentos en la collection players con datos básicos (nombre, apellido, posición, fecha de nacimiento, etc).
  >>    db.players.insert({"name":"Carlitos", "lastname":"Tevez", "position":"delantero","shirt number":10})

  >>    db.players.insert({"name":"Diego", "lastname":"Maradona", "position":"delantero","shirt number":10})

  >>    db.players.insert({"name":"Esteban", "lastname":"Andrada", "position":"Arquero","shirt number":1})

  >>    db.players.insert({"name":"Carlos", "lastname":"Izquierdos", "position":"defensor","shirt number":4})

  >>    db.players.insert({"name":"Licha", "lastname":"Lopez", "position":"defensor","shirt number":6})

>6.  Listar todos los documentos de la collection players. 

  >> db.players.find()
  >>> { "_id" : ObjectId("5f918f2668bc433b4cecf882"), "name" : "Carlitos", "lastname" : "Tevez", "position" : "delantero", "shirt number" : 10 } </br>
{ "_id" : ObjectId("5f918fb468bc433b4cecf883"), "name" : "Diego", "lastname" : "Maradona", "position" : "delantero", "shirt number" : 10 } </br>
{ "_id" : ObjectId("5f91905468bc433b4cecf884"), "name" : "Esteban", "lastname" : "Andrada", "position" : "Arquero", "shirt number" : 1 } </br>
{ "_id" : ObjectId("5f91908c68bc433b4cecf885"), "name" : "Carlos", "lastname" : "Izquierdos", "position" : "defensor", "shirt number" : 4 } </br>
{ "_id" : ObjectId("5f9190a868bc433b4cecf886"), "name" : "Licha", "lastname" : "Lopez", "position" : "defensor", "shirt number" : 6 } </br>

>7.  Crear otras collections con documentos (ej. teams, games, etc). 

  >> db.createCollection("teams") </br>
      { "ok" : 1 } </br>
  >> db.createCollection("games") </br>
      { "ok" : 1 } </br>

