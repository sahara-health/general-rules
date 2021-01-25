# General-rules

General rules to be considered when you start developing on the sahara health architecture.

## Kubernetes pre set-up

#### Previous dependencies (Install in order):

- docker [Installation](https://docs.docker.com/engine/install/ubuntu/)
- kubectl [Installation](https://kubernetes.io/docs/tasks/tools/install-kubectl/)
- minikube [Installation](https://minikube.sigs.k8s.io/docs/start/)

## Build and push docker-images

#### Build: With one simple command you can build the image

`docker build [dockerfile path] -t [image name]`

#### Push:

` docker push [image name]`

the image name must be: `saharahealth/[some name]`

## Kubernetes coninuous local development

We are going to make it a little bit manually, but it has to be always the same so we can define it here.

We have these things:

- yaml files
- dockerfiles

...and nothing else, very easy

First, we have to develop on our git cloned folders from github or azure repos, once you want to debug the app [build and push the docker image](##build-docker-images). At this moment you already have the image on the remote repo and the minikube cluster running locally, finally you have to re-apply the yml files of kubernetes that you are changing (because it has to pull the image you've just modified)

### Memory helper:

- Develop
- [build and push the docker image](##build-docker-images)
- re-apply yaml files
