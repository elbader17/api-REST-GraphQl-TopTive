# Docker


To run the project you need to have [docker](https://docs.docker.com/engine/install/ubuntu/) and [docker-compose](https://docs.docker.com/compose/install/) previously installed

1. `git clone https://github.com/elbader17/api-REST-GraphQl-TopTive.git`
2. `cd api-REST-GraphQl-TopTive`
3. `sudo docker-compose pull`
4. `sudo docker-compose up -d`
5. `sudo docker-compose logs --tail=all -f | grep strapi`


## Routes

The API will run at `http://localhost:1337/` 

-----------------------------------------------------------------------------------------
**COMPETITION**:

**count**
**GET**: /competitions/count

**create**
**POST**:/competitions

**delete**
**DELETE**:/competitions/:id

**find**
**GET**:/competitions

**findone**
**GET**:/competitions/:id

**update**
**PUT**: /competitions/:id

-------------------------------------------------------------------------------------
**PLAYER**:

**count**
**GET**: /players/count

**create**
**POST**:/players

**delete**
**DELETE**:/players/:id

**find**
**GET**:/players

**findone**
**GET**:/players/:id

**update**
**PUT**: /players/:id

---------------------------------------------------------------------------------------

**TEAM**:

**count**
**GET**: /teams/count

**create**
**POST**:/teams

**delete**
**DELETE**:/teams/:id

**find**
**GET**:/teams

**findone**
**GET**:/teams/:id

**update**
**PUT**: /teams/:id

-----------------------------------------------------------------------------------------

## GraphQl

The API also supports graphql, you can access it through this path `http://localhost:1337/graphql`

example

    query{
      competition(id:1){
        name
      	teams{
          name
          shortName
          players{
            name
            
          }
        }
      }
    }

response

    {
      "data": {
        "competition": {
          "name": "libertadores",
          "teams": [
            {
              "name": "boca jr",
              "shortName": "bca",
              "players": [
                {
                  "name": "carlitos"
                }
              ]
            }
          ]
        }
      }
    }
