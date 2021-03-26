Container image creation:
docker build -t simple:1.0.0 -f Dockerfile .
az acr build -t simple:1.0.0 -r simplebcc -f Dockerfile . 