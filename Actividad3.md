SeminarioMongoDB

Actividad 3

1)Utilizar la misma base de datos de películas e insertar varias películas con distinto contenido.

    db.movies.insertMany([
    {
        title: "Billy Elliot", 
        year: 2000, 
        rating: 4.6, 
        gender: "Danza/Drama",
        description: "En Inglaterra, en medio de una crisis minera, un joven de clase trabajadora descubre su talento para el baile con la ayuda de una estricta profesora de         ballet",
        actors: ["Jamie Bell", "Julie Walters", "Gary Lewis", "Jamie Draven"],
        country: "Reino Unido",
        income: 450000,
        duration: 110
    },
    {
        title: "Birdman", 
        year: 2014, 
        rating: 2.6, 
        gender: "Romance/Comedia",
        description: "Un actor pasado de moda, que triunfó en el pasado encarnando a un superhéroe, intenta recuperar la gloria perdida montando una obra en Broadway.",
        actors: ["Michael Keaton", "Zach Galifianakis", "Edward Norton", "Andrea Riseborough", "Amy Ryan"],
        country: "Estados Unidos",
        income: 230000,
        duration: 119
    },
    {
        title: "Roma", 
        year: 2018, 
        rating: 3.2, 
        gender: "Drama",
        description: "En la colonia Roma, de Ciudad de México, dos empleadas domésticas ayudan a una madre a criar a sus cuatro hijos durante las largas ausencias de su               esposo. Una de las jóvenes, Cleo, se hace cargo de los niños como si fueran propios, a pesar de estar atravesando un momento difícil.",
        actors: ["Yalitza Aparicio", "Marina de Tavira"],
        country: "México",
        income: 130000,
        duration: 135
    },
    {
        title: "The Truman Show", 
        year: 1998, 
        rating: 3.9, 
        gender: "Drama/Comedia",
        description: "Truman Burbank, un feliz agente de seguros, cree llevar una vida normal, pero no tiene idea de que las cámaras lo graban las 24 horas y que todo lo que         hace se ve en televisión",
        actors: ["Jim Carrey", "Ed Harris", "Laura Linney", "Noah Emmerich", "Natascha McElhone"],
        country: "Estados Unidos",
        income: 270000,
        duration: 103
    },
    {
        title: "Forrest Gump", 
        year: 1994, 
        rating: 4.1, 
        gender: "Romance/Drama",
        description: "Forrest Gump, un joven sureño, tenaz e inocente, es protagonista de acontecimientos cruciales en la historia de los Estados Unidos.",
        actors: ["Tom Hanks", "Robin Wright", "Gary Sinise", "Mykelti Williamson", "Sally Field"],
        country: "Estados Unidos",
        income: 4100000,
        duration: 142
    },
    {
        title: "Bastardos sin gloria", 
        year: 2009, 
        rating: 4.6, 
        gender: "Bélico/Acción",
        description: "Es el primer año de la ocupación alemana de Francia. El oficial aliado, teniente Aldo Raine, ensambla un equipo de soldados judíos para cometer actos           violentos en contra de los nazis, incluyendo la toma de cabelleras. Él y sus hombres unen fuerzas con Bridget von Hammersmark, una actriz alemana y agente encubierto,         para derrocar a los líderes del Tercer Reich. Sus destinos convergen con la dueña de teatro Shosanna Dreyfus, quien busca vengar la ejecución de su familia.",
        actors: ["Brad Pitt", "Christoph Waltz", "Michael Fassbender", "Eli Roth", "Diane Kruger"],
        country: "Alemania",
        income: 4100000,
        duration: 153
    }
    ])

2)Listar todas las películas del año 2018.

    db.movies.find({year: 2018})

3)Listar las 10 primeras películas de Hollywood.

    db.movies.find({country: "Estados Unidos"}).limit(10)

4)Listar las 5 películas más taquilleras.

    db.movies.find({},{title: 1, income:1, _id:0}).sort({ income:-1}).limit(5)

5)Listar el 2do conjunto de 5 películas más taquilleras.

    db.movies.find({},{title: 1, income:1, _id:0}).sort({ income:-1}).skip(5).limit(5)

6)Repetir query 3 y 4 pero retornando sólo el título y genre.
    
    db.movies.find({country: "Estados Unidos"},{title: 1, gender:1, _id:0}).limit(10)

    db.movies.find({},{title: 1, gender:1, _id:0}).sort({ income:-1}).limit(5)

7)Mostrar los distintos países que existen en la base de datos.

    db.movies.distinct("country")
