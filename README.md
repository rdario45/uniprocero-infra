README.md


# frontend/
npm run build

# infra/

## postgresql
### develop
docker run --name postgress-db -e POSTGRES_USER=admin -e POSTGRES_PASSWORD=123 -e POSTGRES_DB=dev -p 5432:5432 -d postgres
### production
docker run --name postgress-db -e POSTGRES_USER=admin -e POSTGRES_PASSWORD=123 -e POSTGRES_DB=pdn -p 5432:5432 -d postgres


## nginx
### develop
docker run --name nginx-ws -v /Users/s4n/workspace/uniandes/frontend/build:/usr/share/nginx/html -v /Users/s4n/workspace/uniandes/infra/nginx/nginx.conf:/etc/nginx/nginx.conf:ro -d --network host nginx
### production
docker run --name nginx-ws -v /home/SIS/rd.fernandez/proyecto0/frontend/build:/usr/share/nginx/html -v /home/SIS/rd.fernandez/proyecto0/infra/nginx/nginx.conf:/etc/nginx/nginx.conf:ro -d --network host nginx

# backend/
sbt dist
unzip ./target/universal/eventos-1.0.zip
setsid nohup ./eventos-1.0/bin/eventos &
