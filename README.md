README.md

* Database: Postgress

develop:
	docker run --name postgress-db -e POSTGRES_USER=admin -e POSTGRES_PASSWORD=123 -e POSTGRES_DB=dev -p 5432:5432 -d postgres

production:
	docker run --name postgress-db -e POSTGRES_USER=admin -e POSTGRES_PASSWORD=17201413 -e POSTGRES_DB=pdn -p 5432:5432 -d postgres


* WebServer and Proxy reverse: Nginx

develop and prod:
	NGINX_FOLDER="/home/ruben/workspace/uniandes/proyecto0/infra/nginx" && \
	docker run --name nginx-ws -v ${NGINX_FOLDER}/nginx.conf:/etc/nginx/nginx.conf:ro -d --network host nginx



docker plugin install weaveworks/net-plugin:latest_release

docker plugin disable weaveworks/net-plugin:latest_release

docker plugin set weaveworks/net-plugin:latest_release WEAVE_PASSWORD=123 WEAVE_MULTICAST=1

docker plugin enable weaveworks/net-plugin:latest_release

docker network create --driver weave custom-driver-1






docker network create frontend

docker network create backend

docker-compose up -d

docker-compose down

# backend/
rm -rf ./eventos-1.0
sbt dist
unzip ./target/universal/eventos-1.0.zip
./eventos-1.0/bin/eventos












docker network create --driver weave custom-driver-1



    #container_name: nginx-pdn

    #hostname: webserver
#  networks:
#    - frontend

    #container_name: "eventos-pdn"



        #hostname: eventos
#    networks:
#      - frontend
#      - backend


    #container_name: "postgresql-pdn"



 #   networks:
 #     - backend
#  backend:
#    container_name: "backend-prod"
#    build:
#      context: /home/ruben/workspace/uniandes/proyecto0/backend
#      dockerfile: Dockerfile
#    ports:
#      - 9001:9001
#    networks:
#      - webnet
#  npm-build:
#    container_name: npm-build
#    build:
#      context: /home/ruben/workspace/uniandes/proyecto0/frontend
#      dockerfile: Dockerfile
#    volumes:
#      - /home/ruben/workspace/uniandes/proyecto0/frontend:/app
#      - /app/node_modules
#networks:
#  frontend:
#  backend:



#networks:
#  default:
