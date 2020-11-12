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

    db.players.insert({"surname": "Messi", "name": "Leonel", "age": 33, "position": 10})
    db.players.insert({"surname": "Paredes", "name": "Leandro", "age": 26, "position": 8})
    db.players.insert({"surname": "Aguero", "name": "Sergio", "age": 32, "position": 10})
    db.players.insert({"surname": "Dybala", "name": "Paulo", "age": 26, "position": 10})
    db.players.insert({"surname": "Otamendi", "name": "Nicolas", "age": 32, "position": 30})

6)Listar todos los documentos de la collection players.

    db.players.find()
    
7)Crear otras collections con documentos (ej. teams, games, etc).

    db.createCollection("games")
    
    db.games.insert({"date": "30/01/2020", "place": "Mar del Plata", "opponent": "Brasil"})
    db.games.insert({"date": "01/11/2020", "place": "Tandil", "opponent": "Uruguay"})

    
