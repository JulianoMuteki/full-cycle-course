# full-cycle-course
Docker image test with Go

## Build image and push
docker build -t go-full-cycle -f Dockerfile .
docker tag go-full-cycle:latest juliano373pestili/fullcycle:latest
docker push juliano373pestili/fullcycle:latest

# Test image
docker run juliano373pestili/fullcycle

