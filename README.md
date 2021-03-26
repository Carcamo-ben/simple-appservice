Container image creation: \n
docker build -t simple:1.0.0 -f Dockerfile . \n
az acr build -t simple:1.0.0 -r simplebcc -f Dockerfile . 
