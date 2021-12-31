# [GraphQL](https://graphql.org/)

Para empezar a utilizarlo vamos a tener que crear un servidor.

E este caso usaremos una base de datos de [mongodb](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/) e iniciamos el servidor con el comando.
- iniciar servidor de mongo
```
sudo systemctl start mongod
```
si sale un error `Failed to start mongod.service: Unit mongod.service not found.` por el codigo anterior, ejecutar:
```
sudo systemctl daemon-reload
```

- status de mongo
```
sudo systemctl status mongod
```

- Opcionalmente, puede asegurarse de que MongoDB comenzará después de un reinicio del sistema emitiendo el siguiente comando:
```
sudo systemctl enable mongod
```

- Detener MONGODB:
```
sudo systemctl stop mongod
```

- Reiniciar MONGODB:
```
sudo systemctl restart mongod
```

- Inicie una mongoshsesión en la misma máquina host que mongod. Puede ejecutar mongosh sin ninguna opción de línea de comandos para conectarse a un mongodservidor que se está ejecutando en su host local con el puerto predeterminado 27017.

activa el shiel de mongo
```
mongosh
```