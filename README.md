# Node technologies

Building a Web API with Node.js

## Requirements

- Install [Node](http://nodejs.org)
- Install [git](http://git-scm.com/downloads)
- NPM global modules:
  - npm install -g gulp bunyan json

### 01 Basic Server

    cd 01-basic_server
    node index.js

<http://localhost:3000>

### 02 Express

    cd 02-express
    npm install
    node index.js

    npm install -g nodemon

<http://localhost:3000>

### 03 Crud

<https://lodash.com/docs>

    npm install -g json


    cd 03-express
    npm install
    nodemon index.js


    curl -s -H "Content-Type: application/json" -X POST -d '{"name":"jessy","age":"3","type":"siamese"}' http://localhost:3000/cat | json

    curl -s -H "Content-Type: application/json" -X POST -d '{"name":"sam","age":"5","type":"alley"}' http://localhost:3000/cat | json

    curl -s -X GET http://localhost:3000/cat | json

    curl -s -H "Content-Type: application/json" -X PUT -d '{"name":"sam","age":"8","type":"alley"}' http://localhost:3000/cat/sam | json

    curl -s -X DELETE http://localhost:3000/cat/sam | json


### 04 MongoDB

<https://www.mongodb.org/downloads>

On Mac I recommend homebrew

    brew up
    brew install mongodb

    cd 04-mongodb
    npm install
    nodemon index.js

    # mongo commands
    show dbs
    use cats
    db.cats.find()
    db.cats.remove({})
    use cats
    db.dropDatabase()

    curl -s -H "Content-Type: application/json" -X POST -d '{"name":"jessy","age":"3","type":"siamese"}' http://localhost:3000/cat | json

    curl -s -H "Content-Type: application/json" -X POST -d '{"name":"sam","age":"5","type":"alley"}' http://localhost:3000/cat | json

    # Gets all cats
    curl -s -X GET http://localhost:3000/cat | json

    # Get one cat
    # Note you have to pass the Object ID
    curl -s -X GET http://localhost:3000/cat/55b79c99ce6dba2494173aef | json

    # Note you have to pass the Object ID
    curl -s -H "Content-Type: application/json" -X PUT -d '{"name":"sam","age":"8","type":"alley"}' http://localhost:3000/cat/55b79c99ce6dba2494173aef | json

    # Note you have to pass the Object ID
    curl -s -X DELETE http://localhost:3000/cat/55b79c99ce6dba2494173aef | json


### 05 Request

<https://github.com/request/request>

    cd 05-request
    npm install

    npm install -g forever

    forever start cat_server.js
    forever start dog_server.js
    forever list

    curl -s -H "Content-Type: application/json" -X POST -d '{"name":"jessy","age":"3","type":"boxer"}' http://localhost:3001/dog | json

    curl -s -H "Content-Type: application/json" -X POST -d '{"name":"sam","age":"5","type":"bulldog"}' http://localhost:3001/dog | json

    curl -s -X GET http://localhost:3001/dog | json

    curl -s -H "Content-Type: application/json" -X PUT -d '{"name":"sam","age":"8","type":"bulldog"}' http://localhost:3001/dog/55ad3cd669e6f045672a1c77 | json

    curl -s -X DELETE http://localhost:3000/dog/ID | json

    nodemon pet_server.js

<http://localhost:3002/pets>

### 06 Async

<https://github.com/caolan/async>

    cd 06-async
    npm install

    forever stopall
    forever start cat_server.js
    forever start dog_server.js
    forever list

    nodemon pet_server.js

<http://localhost:3002/pets>

### 07 Non Blocking

<https://github.com/caolan/async>

    cd 07-non_blocking
    npm install

    forever stopall
    forever start cat_server.js
    forever start dog_server.js
    forever list

    nodemon pet_server.js

<http://localhost:3002/pets>
<http://localhost:3002/ping>

### 08 Redis

<http://redis.io/download>
<http://redis.io/commands>

On Mac I recommend homebrew

    brew up
    brew install redis

    cd 08-redis
    npm install

    forever stopall
    forever start cat_server.js
    forever start dog_server.js
    forever list

    nodemon pet_server.js

    curl -s -H "Content-Type: application/json" -X POST -d '{"name":"jessy","age":"3","type":"siamese"}' http://localhost:3000/cat | json

    curl -s -H "Content-Type: application/json" -X POST -d '{"name":"sam","age":"5","type":"alley"}' http://localhost:3000/cat | json

    curl -s -H "Content-Type: application/json" -X POST -d '{"name":"joe","age":"4","type":"garfield"}' http://localhost:3000/cat | json

    curl -s -H "Content-Type: application/json" -X POST -d '{"name":"mama","age":"9","type":"tabby"}' http://localhost:3000/cat | json

    curl -s -X GET http://localhost:3000/cat | json

<http://localhost:3002/catname/ID>

    # Useful redis commands
    redis-cli
    set key [value]
    get [key]
    keys *
    flushdb
