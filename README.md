# Challenge

this is a sample Roby on Rails app deployed in docker container 
the steps for creating the docker image and docker-compose file are from this blog post https://semaphoreci.com/community/tutorials/dockerizing-a-ruby-on-rails-application

to run the application with docker compose in the drkiq directory run the following commands:
```
docker volume create --name drkiq-postgres
docker volume create --name drkiq-redis

docker-compose up

docker-compose run drkiq rake db:reset
docker-compose run drkiq rake db:migrate

docker-compose up
```
the ruby on rails default page will be available in serverIP:8000

Second part of the repo is the manifest directory wich cotaines kubernetes manifests used to deploy this sample app

to run in kubernetes
```
kubectl create -f manifests
```
the manifests contains deployments files as well as services for postgres , redis , drkiq and sidekiq
to check the pods and services are running
```
kubectl get pods
kubectl get svc
```
now the application is accissable through the service drkiq and port 80
