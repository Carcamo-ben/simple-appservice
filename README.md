Container image creation:
#local
docker build -t simple:1.0.0 -f Dockerfile .
#Azure
az acr build -t simple:1.0.0 -r simplebcc -f Dockerfile . 
