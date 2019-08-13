README.md

* Database: Postgress

develop:
	docker run --name postgress-db -e POSTGRES_USER=admin -e POSTGRES_PASSWORD=123 -e POSTGRES_DB=dev -p 5432:5432 -d postgres

production:
	docker run --name postgress-db -e POSTGRES_USER=admin -e POSTGRES_PASSWORD=17201413 -e POSTGRES_DB=pdn -p 5432:5432 -d postgres


* WebServer and Proxy reverse: Nginx

develop and prod:
	INFRA_FOLDER="/home/ruben/workspace/uniandes/proyecto0/infra" && \
	docker run --name nginx-ws -v ${INFRA_FOLDER}/nginx.conf:/etc/nginx/nginx.conf:ro -d --network host nginx
