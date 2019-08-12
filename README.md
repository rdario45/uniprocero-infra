README.md






run webserver

PROJECT_FOLDER="/home/ruben/workspace/uniandes/proyecto0" && \
docker run --name nginx-ws -v ${PROJECT_FOLDER}/nginx.conf:/etc/nginx/nginx.conf:ro -d --network host nginx