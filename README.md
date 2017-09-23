# Challenge

to run the application with docker compose:
'''
docker volume create --name drkiq-postgres
docker volume create --name drkiq-redis

docker-compose up

docker­-compose run drkiq rake db:reset
docker­-compose run drkiq rake db:migrate

docker-compose up
'''
the ruby on rails default page will be available in serverIP:8000
