# kubernetes-demo
---

- Build image
`docker build -t gcr.io/$PROJECT_ID/hello-node:v1 .`
  - Build and image of the contents of the current directory, and tag it.
  - In GKE, this image would be pulled from the Docker registry using `docker pull`
- Running container
`docker run -d -p 8000:8080 gcr.io/$PROJECT_ID/hello-node:v1`
  - `-p` publishes port 8080 on the container to port 8000 on the host machine.
  - `-d` will detach and run the container in the background.
- To stop the container
  - Grab the container ID by running `docker ps` and invoke `docker stop <CONTAINER ID>`
- Push to Google Cloud Repo
`gcloud docker push gcr.io/$PROJECT_ID/hello-node:v1`
