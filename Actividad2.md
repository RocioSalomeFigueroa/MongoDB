SeminarioMongoDB

Actividad 2

1)Crear una nueva base de datos de un sistema de streaming de video (ej. Netflix, Flow, Amazon Prime) que permita almacenar movies.

    use netflix
    db.createCollection("movies")

2)Para cada movie, se debería guardar información como título (String), year (Number), rating (Number, entre 1.0 y 5.0), genre (String), description (String), 
actors (Array<String>), country (String), income (Number), duration (Number).

3)Agregar películas usando insert(), insertOne() & insertMany().

     db.movies.insert({
            title: "Black Panther", 
            year: 2018, 
            rating: 4.0, 
            gender: "Accion/Aventura",
            description: "Despues de morir su padre, TChalla regresa a su nacion, Wakanda. Una vez alli, descubre que tiene un nuevo y terrible enemigo, y TChalla asume la personalidad de Pantera Negra para salvar no solo al reino de Wakanda, sino a toda la humanidad",
            actors: ["Chadwick Boseman", "Michael B. Jordan", "Danai Gurira", "Lupita Nyongo", "Martin Freeman"],
            country: "Estados Unidos",
            income: 210000,
            duration: 134 
    })
    
        
    db.movies.insertOne({
            title: "Spider-Man: lejos de casa", 
            year: 2019, 
            rating: 4.5, 
            gender: "Accion/Aventura",
            description: "Peter Parker decide pasar unas merecidas vacaciones en Europa junto a MJ, Ned y el resto de sus amigos. Sin embargo, Peter debe volver a ponerse el traje de Spider-Man cuando Nick Fury le encomienda una nueva mision: frenar el ataque de unas criaturas que están causando el caos en el continente",
            actors: ["Tom Holland", "Samuel L. Jackson", "Zendaya", "Cobie Smulders", "Jon Favreau"],
            country: "Estados Unidos",
            income: 2120000,
            duration: 130  
    })
    

    db.movies.insertMany([
        {
            title: "Doctor Strange: hechicero supremo", 
            year: 2016, 
            rating: 4.5, 
            gender: "Accion/Fantasia",
            description: "Despues de sufrir un accidente, un brillante y arrogante cirujano busca rehabilitarse mediante tecnicas alternativas. Sus intentos le llevan a descubrir que ha sido designado para encabezar la lucha contra una fuerza oscura y sobrenatural",
            actors: ["Benedict Cumberbatch", "Chiwetel Ejiofor", "Rachel McAdams", "Benedict Wong", "Michael Stuhlbarg"],
            country: "Estados Unidos",
            income: 10000,
            duration: 115
        },
        {
            title: "Thor: un mundo oscuro", 
            year: 2013, 
            rating: 4.2, 
            gender: "Accion/Fantasia",
            description: "Malekith, un enemigo mas antiguo que el universo, regresa a la Tierra para cumplir su plan destructor. Thor debe enfrentarse a un rival al que ni siquiera Odin parece poder detener y, desesperado, libera a su hermano Loki para que lo ayude",
            actors: ["Chris Hemsworth", "Natalie Portman", "Tom Hiddleston", "Anthony Hopkins", "Stellan Skarsgard"],
            country: "Estados Unidos",
            income: 20000,
            duration: 112 
        },
        {
            title: "Iron Man 3", 
            year: 2013, 
            rating: 4.8, 
            gender: "Accion/Aventura",
            description: "El descarado y brillante Tony Stark, tras ver destruido todo su universo personal, debe encontrar y enfrentarse a un enemigo cuyo poder no conoce limites. Este viaje pondra a prueba su entereza una y otra vez, y le obligara a confiar en su ingenio.",
            actors: ["Robert Downey Jr", "Gwyneth Paltrow", "Don Cheadle", "Guy Pearce", "Rebecca Hall"],
            country: "Estados Unidos",
            income: 50000,
            duration: 131 
        },
        {
            title: "Ant-Man: el Hombre Hormiga", 
            year: 2015, 
            rating: 3.8, 
            gender: "Accion/Aventura",
            description: "Un ladron con la habilidad de encogerse de tamanio pero crecer en fuerza debe sacar su heroe interior y ayudar a su mentor a llevar a cabo un plan para salvar al mundo.",
            actors: ["Paul Rudd", "Michael Douglas", "Evangeline Lilly", "Judy Greer"],
            country: "Estados Unidos",
            income: 30000,
            duration: 117 
        }
      ])

4)Actualizar películas agregando el field highlighted=true a aquellas con rating > 4.5.

    db.movies.updateMany(
        { rating: {$gt: 4.5} },
        { 
        $set: {
            highlighted: true
        }
        })

5)Actualizar películas cambiando el genre “drama” por “bored”.(como no tenia drama, use Accion/Aventura y lo cambie por Accion)

    db.movies.updateMany(
        { gender: "Accion/Aventura" },
        { 
        $set: {
            gender: "Accion"
        }
    })

6)Borrar todas las películas que tengan más de 30 años.(modifique esta consigna en vez de que borre las de 30 años, borro las de 5 años)
    
    db.movies.deleteMany({year: {$lt: 2020 - 5 }})

7)Buscar todas las películas argentinas.

    db.movies.find({country: "Argentina"})

8)Buscar todas las películas de acción con un buen rating (ej. > 4.0) que hayan salido los últimos 2 años.

    db.movies.find({gender: "Accion", rating: {$gt: 4.0}, year:{$gte: 2020 - 2}})

