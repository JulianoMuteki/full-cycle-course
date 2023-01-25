##
## STEP 1 - BUILD

# specify the base image to  be used for the application with mod 
FROM golang:1.8 AS build

# create a working directory inside the image
WORKDIR /app

COPY /files/fullcycle.go .
RUN go build -o full-cycle .
 
# compile application
RUN CGO_ENABLED=0 go build -o /full-cycle -ldflags="-w -s"

##
## DEPLOY
##
FROM scratch

WORKDIR /

COPY --from=build /full-cycle /full-cycle

ENTRYPOINT ["/full-cycle"]