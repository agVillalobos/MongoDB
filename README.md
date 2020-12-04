
Pagina mongo
	-https://www.mongodb.com/

robomongo interfaz grafica
	-https://robomongo.org/

crear folder en C:
	-data->db

Ejecutar el proceso que esta en:
	- C:\Program Files\MongoDB\Server\3.6\binmongod.exe para levantar mongo.
	
MongoDB in Docker
    docker pull mongo
    docker run --rm -d  -p 27017:27017/tcp mongo:latest//levanta contenedor y elimina cuando lo pares
    docker exec -it mongo bash
    docker exec -it condescending_albattani bash
    docker rm core-counter//elimina contenedor
    mongo
Robo3T(interfaz para conectar con mongo)
    localhost 27017
Url
http://localhost:27017/

MongoDB
    Multiplataforma
    high performance
    hiigh availability
    easy scalability

Cuando Usar NoSQL
    Aplicacion con crecimiento rapido    
    La aplicacion va a tener servidores en la nube
    Montar una bd rapido.
    datos con diferentes estructuras
    dinamica
    muchos usuuarios accediendo al mismo tiempo

Como funciona
    BD-> Colecciones-> Documentos-> JSON
    llave-valor

MongoDB commands
    use dbs
    //crea bd
    use test
    
    //crea una coleccion.
    db.people.save({firstname:"Nic", lastname:"Raboy"})
    db.usuarios.insert({"cedula":"3","name":"test"})
    db.productos.insert({
        "id":"1",
        "nombre":"camiseta",
        "valor": 20
    })
    
    //muestra colecciones
    show collections
    
    //elimina colecciones
    db.usuarios.drop()
    
    //borra una bd
    use {database_name}
    db.dropDatabase()
    
    //Consultas
    db.people.find().pretty()
    db.people.find({})
    db.productos.find({"valor":15.0})//igual
    db.productos.find({"valor":{$lt: 19.0}})//menor que
    db.productos.find({"valor":{$lte: 19.0}})//menor o igual que
    db.productos.find({"valor":{$gt: 19.0}})//mayor que
    db.productos.find({"valor":{$gte: 19.0}})//mayor o igual que
    db.productos.find({"valor":{$new: 19.0}})//no es igual
    {{key1:value1, key2:value2}}

    db.productos.find().limit(1)
    db.productos.find().sort({valor:1})//menor a mayor
    db.productos.find().sort({valor:-1})//mayor a menor
    
    //Updating
    db.productos.update({
        "id":"1"},
        {
            $set : {'valor': 20.45}
        })
    
    //Eliminar document
    db.productos.deleteOne({
        "id":"1"
    })
    
    //Sale del programa
    exit

MongoDB with Net Core
    https://docs.microsoft.com/en-us/aspnet/core/tutorials/first-mongo-app?view=aspnetcore-3.1&tabs=visual-studio