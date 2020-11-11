SeminarioMongoDB

Actividad 1

1)Instalar MongoDB en ambiente local
    mongod
  
2)Conectarse a MongoDB vía CLI.
    mongo
  
3)Crear una nueva base de datos llamada futbolfifa.
    use futbolFifa (la crea si no existe o la utiliza si ya estaba creada)
  
4)Crear una nueva collection llamada players.
    db.createCollection("players")

5)Insertar 5 documentos en la collection players con datos básicos (nombre, apellido, posición, fecha de nacimiento, etc).
    db.players.insert({"Apellido": "Messi", "Nombre": "Leonel", "Edad": 33, "posicion": 10})
    db.players.insert({"Apellido": "Paredes", "Nombre": "Leandro", "Edad": 26, "posicion": 8})
    db.players.insert({"Apellido": "Aguero", "Nombre": "Sergio", "Edad": 32, "posicion": 10})
    db.players.insert({"Apellido": "Dybala", "Nombre": "Paulo", "Edad": 26, "posicion": 10})
    db.players.insert({"Apellido": "Otamendi", "Nombre": "Nicolas", "Edad": 32, "posicion": 30})

6)Listar todos los documentos de la collection players.
    db.players.find()
    
7)Crear otras collections con documentos (ej. teams, games, etc).
    db.createCollection("games")
    
    db.games.insert({"Fecha": "30/01/2020", "Lugar": "Mar del Plata", "Rival": "Brasil"})
    db.games.insert({"Fecha": "01/11/2020", "Lugar": "Tandil", "Rival": "Uruguay"})
