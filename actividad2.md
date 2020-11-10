# ACTIVIDAD 2: 
  ## 1.  Crear una nueva base de datos de un sistema de streaming de video (ej. Netflix, Flow, Amazon Prime) que permita almacenar movies.  </br> 
  >> use netflix
  ## 2.  Para cada movie, se debería guardar información como título (String), year (Number), rating (Number, entre 1.0 y 5.0), genre (String), description (String), actors (Array<String>), country (String), income (Number), duration (Number).  </br> 
  >> db.createCollection("movies")
  ## 3.  Agregar películas usando insert(), insertOne() & insertMany().  </br> 
  >> db.movies.insert(
    {
        "titulo": "The Simpsons",
        "year": 2007,
        "rating": 5.0,
        "genre": "Cartoon",
        "description": "Thanks to Lisa Simpson, Lake Springfield is cleaned up from the pollution that once fouled it. But when Homer, who's adopted a pig (Spider-pig) and dumps a silo full of the pig's crap in the lake, the EPA places a large dome over Springfield, and the Simpsons family manage to escape through a sinkhole.",
        "actors": ["Homer S", "Marge S", "Bart S", "Lisa S", "Maggie S"],
        "country": "USA",
        "income": 200000,
        "duration": 88
    })
  ## 4.  Actualizar películas agregando el field highlighted=true a aquellas con rating > 4.5.  </br> 
  ## 5. 	Actualizar películas cambiando el genre “drama” por “bored”.  </br> 
  ## 6. 	Borrar todas las películas que tengan más de 30 años.  </br> 
  ## 7. 	Buscar todas las películas argentinas.  </br> 
  ## 8.  Buscar todas las películas de acción con un buen rating (ej. > 4.0) que hayan salido los últimos 2 años.  </br>
