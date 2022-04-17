docker-compose build
docker-compose run --rm rails bash

docker-compose run --rm rails rails new . --database=postgresql
or 
docker-compose run --rm rails rails new . --api --database=postgresql

docker-compose run --rm rails bundle install


---
rails new . --force --database=postgresql
bundle install
exit
---

*edit ./config/database.yml for  setting postgresql



docker-compose up

---

permission 

sudo chown username:username .


