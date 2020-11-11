# ACTIVIDAD 2: 
  ## 1.  Crear una nueva base de datos de un sistema de streaming de video (ej. Netflix, Flow, Amazon Prime) que permita almacenar movies.  </br> 
  >> use netflix
  ## 2.  Para cada movie, se debería guardar información como título (String), year (Number), rating (Number, entre 1.0 y 5.0), genre (String), description (String), actors (Array<String>), country (String), income (Number), duration (Number).  </br> 
  >> db.createCollection("movies")
  ## 3.  Agregar películas usando insert(), insertOne() & insertMany().  </br> 
  >> db.movies.insert(  </br>
    { </br>
        "titulo": "The Simpsons", </br>
        "year": 2007, </br>
        "rating": 5.0, </br>
        "genre": "Cartoon", </br> 
        "description": "Thanks to Lisa Simpson, Lake Springfield is cleaned up from the pollution that once fouled it. But when Homer, who's adopted a pig (Spider-pig) and dumps a silo full of the pig's crap in the lake, the EPA places a large dome over Springfield, and the Simpsons family manage to escape through a sinkhole.", </br>
        "actors": ["Homer S", "Marge S", "Bart S", "Lisa S", "Maggie S"], </br>
        "country": "USA", </br>
        "income": 200000, </br>
        "duration": 88 </br>
    }) </br> 
 >>> WriteResult({ "nInserted" : 1 })
    
 >> db.movies.insertOne(  </br>
    { </br>
      "titulo": "Up", </br>
      "year": 2009, </br>
      "rating": 4.9, </br>
      "genre": "Cartoon", </br>
      "description": "Little kid joins senior citizen in a dream search", </br>
      "actors": ["Russel", "Carl", "Dug", "Ellie"],  </br>
      "country": "USA", </br>
      "income": 398290, </br>
      "duration": 96 </br>
    }) </br>
  >>> {"acknowledged" : true, "insertedId" : ObjectId("5fab50973bec59743dee5bfb")} 
    
  >> db.movies.insertMany([{ </br>
      "titulo": "Toy Story", </br>
      "year": 1995, </br>
      "rating": 4.3, </br>
      "genre": "Cartoon", </br>
      "description": "Little adventures that toys have when nobody is looking", </br>
      "actors": ["Woody", "Betty", "Buzz Lightyear", "Tiro al Blanco"],  </br>
      "country": "USA", </br>
      "income": 498427, </br>
      "duration": 100 </br>
      }, </br>
      { </br>
      "titulo": "Toy Story 2", </br>
      "year": 1999, </br>
      "rating": 5.0, </br>
      "genre": "Drama", </br>
      "description": "Toys have to solve some adventures while Andy's not looking", </br>
      "actors": ["Woody", "Betty", "Buzz Lightyear", "Tiro al Blanco", "Jessie","Oloroso Pete"],  </br>
      "country": "USA", </br>
      "income": 231234, </br>
      "duration": 92 </br>
    }]) </br>
   >>> {
	"acknowledged" : true,
	"insertedIds" : [
		ObjectId("5fab50a43bec59743dee5bfc"),
		ObjectId("5fab50a43bec59743dee5bfd")
	]
}
    
  ## 4.  Actualizar películas agregando el field highlighted=true a aquellas con rating > 4.5.  </br> 
   >> db.movies.updateMany( {rating: {$gt: 4.5}}, {$set: {highlighted: true}} ) 
   >>> { "acknowledged" : true, "matchedCount" : 3, "modifiedCount" : 3 }
  
  ## 5. 	Actualizar películas cambiando el genre “drama” por “bored”.  </br> 
   >> db.movies.updateMany( { genre: "Drama" }, { $set: { genre: "Bored"}} )
   >>> { "acknowledged" : true, "matchedCount" : 1, "modifiedCount" : 1 }
  
  ## 6. 	Borrar todas las películas que tengan más de 30 años.  </br> 
   >> db.movies.deleteMany({year: {$lt: new Date().getFullYear() - 30}})
   >>> { "acknowledged" : true, "deletedCount" : 0 }
   
  ## 7. 	Buscar todas las películas argentinas.  </br> 
   >> db.movies.find ({country: "Argentina"})
  
  ## 8.  Buscar todas las películas de acción con un buen rating (ej. > 4.0) que hayan salido los últimos 2 años.  </br>
   >> db.movies.find({  </br> 
    genre: "Action", </br> 
    rating: {$gt: 4.2}, </br> 
    year: {$gt: new Date().getFullYear() - 2} </br> 
    }) </br> 
  
