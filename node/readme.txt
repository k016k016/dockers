
[react]
docker-compose build
docker-compose run --rm node sh
---
npx create-react-app .
exit
---
docker-compose up
---


[next.js]
docker-compose build
docker-compose run --rm node sh
---
npx create-next-app@latest .
exit
---

*if you use next.js then edit docker-compose.yml 
    command: sh -c "PORT=3000 npm run dev"


docker-compose up
---





permission 
sudo chown username:username .



