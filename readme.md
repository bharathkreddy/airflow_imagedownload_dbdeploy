# deploys an airflow container which executes bash and python operators 
## objective is to extract data on allupcomming rocket launches by hitting the api : https://ll.thespacedevs.com/2.0.0/launch/upcoming
## Prase the json and extract the image url , save and recursively download all images and save those down to a foler
## create an instance of mongodb and store all this data on the db
## deploy a webui for users to search and interact with the data.
docker run -ti -p 8080:8080 -v /home/bharath/Desktop/brk/rocket.py:/opt/airflow/dags/rocket.py --entrypoint=/bin/bash --name airflow apache/airflow:2.0.0-python3.8 -c '(airflow db init && airflow users create --username Admin --password Admin --firstname brk --lastname brk --role Admin --email admin@example.com); airflow webserver & airflow scheduler'
