# ACTIVIDAD 3:
  ## 1.  Utilizar la misma base de datos de películas e insertar varias películas con distinto contenido. </br> 
  >> db.movies.insertMany([  </br>
      { </br>
      "titulo": "El Clan", </br>
      "year": 2015, </br>
      "rating": 3.0, </br>
      "genre": ["Drama", "Police"], </br>
      "description": "Esta basada en la historia real de la familia Puccio, trata sobre un secuestro", </br>
      "actors": ["Guillermo Francella","Antonia Bengoechea","Pedro Lanzani"],  </br>
      "country": "Argentina", </br>
      "income": 32197, </br>
      "duration": 110 </br>
      }, </br>
      { </br>
      "titulo": "Moana", </br>
      "year": 2018, </br>
      "rating": 3.8, </br>
      "genre": "Comedy", </br>
      "description": "Moana looks for the heart of te fiti under the sea", </br>
      "actors": ["Moana", "Hei Hei", "Jefe Tui", "Tamatoa"],  </br>
      "country": "New Zealand", </br>
      "income": 368291, </br>
      "duration": 120 </br>
      }, </br>
      { </br>
      "titulo": "Bob Esponja al rescate", </br>
      "year": 2020, </br>
      "rating": 2.7, </br>
      "genre": ["Comedy", "Drama", "Kids"], </br>
      "description": "Thes story of Bob Esponja", </br>
      "actors": ["Bob Esponja", "Patricio Estrella", "Arenita", "Calamardo"],  </br>
      "country": "Under the Sea", </br>
      "income": 62413, </br>
      "duration": 90 </br>
      }  </br>
      ]) </br>
 >>> {"acknowledged" : true, </br>
      "insertedIds" : [ ObjectId("5fab56a53bec59743dee5bfe"),   </br>
                        ObjectId("5fab56a53bec59743dee5bff"),   </br>
                        ObjectId("5fab56a53bec59743dee5c00")   </br>
                        ]} </br>
  
  ## 2.  Listar todas las películas del año 2018. </br> 
  >> db.movies.find({year: 2018})
  >>> { "_id" : ObjectId("5fab56a53bec59743dee5bff"), </br>
  "titulo" : "Moana", </br>
  "year" : 2018, </br>
  "rating" : 3.8, </br>
  "genre" : "Comedy", </br>
  "description" : "Moana looks for the heart of te fiti under the sea", </br>
  "actors" : [ "Moana", "Hei Hei", "Jefe Tui", "Tamatoa" ], </br>
  "country" : "New Zealand", </br>
  "income" : 368291, </br>
  "duration" : 120 } </br>
  
  ## 3.  Listar las 10 primeras películas de Hollywood. </br> 
  >> db.movies.find({country: "USA"}).limit(10)
  >>>{ "_id" : ObjectId("5fab506a3bec59743dee5bfa"), </br>
  "titulo" : "The Simpsons", </br>
  "year" : 2007, </br>
  "rating" : 5, </br>
  "genre" : "Cartoon", </br>
  "description" : "Thanks to Lisa Simpson, Lake Springfield is cleaned up from the pollution that once fouled it. But when Homer, who's adopted a pig (Spider-pig) and dumps a silo full of the pig's crap in the lake, the EPA places a large dome over Springfield, and the Simpsons family manage to escape through a sinkhole.", </br>
  "actors" : [ "Homer S", "Marge S", "Bart S", "Lisa S", "Maggie S" ], </br>
  "country" : "USA", </br>
  "income" : 200000, </br>
  "duration" : 88, </br>
  "highlighted" : true } </br>
 { "_id" : ObjectId("5fab50973bec59743dee5bfb"), </br>
 "titulo" : "Up", </br>
 "year" : 2009, </br>
 "rating" : 4.9, </br>
 "genre" : "Cartoon", </br> 
 "description" : "Little kid joins senior citizen in a dream search", </br>
 "actors" : [ "Russel", "Carl", "Dug", "Ellie" ],  </br>
 "country" : "USA", </br>
 "income" : 398290, </br>
 "duration" : 96, </br>
 "highlighted" : true } </br>
{ "_id" : ObjectId("5fab50a43bec59743dee5bfc"), </br>
"titulo" : "Toy Story", </br>
"year" : 1995, </br>
"rating" : 4.3, </br>
"genre" : "Cartoon", </br>
"description" : "Little adventures that toys have when nobody is looking", </br>
"actors" : [ "Woody", "Betty", "Buzz Lightyear", "Tiro al Blanco" ], </br>
"country" : "USA", </br>
"income" : 498427, </br>
"duration" : 100 }</br>
{ "_id" : ObjectId("5fab50a43bec59743dee5bfd"), </br>
"titulo" : "Toy Story 2", </br>
"year" : 1999, </br>
"rating" : 5, </br>
"genre" : "Bored", </br>
"description" : "Toys have to solve some adventures while Andy's not looking", </br>
"actors" : [ "Woody", "Betty", "Buzz Lightyear", "Tiro al Blanco", "Jessie", "Oloroso Pete" ], </br>
"country" : "USA", </br>
"income" : 231234, </br>
"duration" : 92, </br>
"highlighted" : true }
  
  ## 4.  Listar las 5 películas más taquilleras. </br> 
  >> db.movies.find().limit(5).sort({income: -1})
  >>>{ "_id" : ObjectId("5fab50a43bec59743dee5bfc"), "titulo" : "Toy Story", "year" : 1995, "rating" : 4.3, "genre" : "Cartoon", "description" : "Little adventures that toys have when nobody is looking", "actors" : [ "Woody", "Betty", "Buzz Lightyear", "Tiro al Blanco" ], "country" : "USA", "income" : 498427, "duration" : 100 }
{ "_id" : ObjectId("5fab50973bec59743dee5bfb"), "titulo" : "Up", "year" : 2009, "rating" : 4.9, "genre" : "Cartoon", "description" : "Little kid joins senior citizen in a dream search", "actors" : [ "Russel", "Carl", "Dug", "Ellie" ], "country" : "USA", "income" : 398290, "duration" : 96, "highlighted" : true }
{ "_id" : ObjectId("5fab56a53bec59743dee5bff"), "titulo" : "Moana", "year" : 2018, "rating" : 3.8, "genre" : "Comedy", "description" : "Moana looks for the heart of te fiti under the sea", "actors" : [ "Moana", "Hei Hei", "Jefe Tui", "Tamatoa" ], "country" : "New Zealand", "income" : 368291, "duration" : 120 }
{ "_id" : ObjectId("5fab50a43bec59743dee5bfd"), "titulo" : "Toy Story 2", "year" : 1999, "rating" : 5, "genre" : "Bored", "description" : "Toys have to solve some adventures while Andy's not looking", "actors" : [ "Woody", "Betty", "Buzz Lightyear", "Tiro al Blanco", "Jessie", "Oloroso Pete" ], "country" : "USA", "income" : 231234, "duration" : 92, "highlighted" : true }
{ "_id" : ObjectId("5fab506a3bec59743dee5bfa"), "titulo" : "The Simpsons", "year" : 2007, "rating" : 5, "genre" : "Cartoon", "description" : "Thanks to Lisa Simpson, Lake Springfield is cleaned up from the pollution that once fouled it. But when Homer, who's adopted a pig (Spider-pig) and dumps a silo full of the pig's crap in the lake, the EPA places a large dome over Springfield, and the Simpsons family manage to escape through a sinkhole.", "actors" : [ "Homer S", "Marge S", "Bart S", "Lisa S", "Maggie S" ], "country" : "USA", "income" : 200000, "duration" : 88, "highlighted" : true }
  ## 5.  Listar el 2do conjunto de 5 películas más taquilleras. </br> 
  >> db.movies.find().limit(5).sort({ income: -1}).skip(5)
  >>> { "_id" : ObjectId("5fab56a53bec59743dee5c00"), "titulo" : "Bob Esponja al rescate", "year" : 2020, "rating" : 2.7, "genre" : [ "Comedy", "Drama", "Kids" ], "description" : "Thes story of Bob Esponja", "actors" : [ "Bob Esponja", "Patricio Estrella", "Arenita", "Calamardo" ], "country" : "Under the Sea", "income" : 62413, "duration" : 90 }
{ "_id" : ObjectId("5fab56a53bec59743dee5bfe"), "titulo" : "El Clan", "year" : 2015, "rating" : 3, "genre" : [ "Drama", "Police" ], "description" : "Esta basada en la historia real de la familia Puccio, trata sobre un secuestro", "actors" : [ "Guillermo Francella", "Antonia Bengoechea", "Pedro Lanzani" ], "country" : "Argentina", "income" : 32197, "duration" : 110 }
  ## 6.  Repetir query 3 y 4 pero retornando sólo el título y genre. </br> 
  >> db.movies.find({country: "USA"}, {title:1,genre:1}).limit(10)
  >>> { "_id" : ObjectId("5fab506a3bec59743dee5bfa"), "genre" : "Cartoon" } </br> 
{ "_id" : ObjectId("5fab50973bec59743dee5bfb"), "genre" : "Cartoon" } </br> 
{ "_id" : ObjectId("5fab50a43bec59743dee5bfc"), "genre" : "Cartoon" } </br> 
{ "_id" : ObjectId("5fab50a43bec59743dee5bfd"), "genre" : "Bored" } </br> 

  >> db.movies.find({},{title:1,genre:1}).limit(5).sort({income: -1}) 
  >>>{ "_id" : ObjectId("5fab50a43bec59743dee5bfc"), "genre" : "Cartoon" }  </br> 
{ "_id" : ObjectId("5fab50973bec59743dee5bfb"), "genre" : "Cartoon" }  </br> 
{ "_id" : ObjectId("5fab56a53bec59743dee5bff"), "genre" : "Comedy" }  </br> 
{ "_id" : ObjectId("5fab50a43bec59743dee5bfd"), "genre" : "Bored" }  </br> 
{ "_id" : ObjectId("5fab506a3bec59743dee5bfa"), "genre" : "Cartoon" }  </br> 
  
  ## 7.  Mostrar los distintos países que existen en la base de datos. </br>
  >> db.movies.distinct("country")
  >>> [ "Argentina", "New Zealand", "USA", "Under the Sea" ]
