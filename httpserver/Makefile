export tag=v1.0
root:
	export ROOT=github.com/kk618/golang

build:
	echo "building httpserver binary"
	mkdir -p bin/amd64
	CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -o bin/amd64 .

release: build
	echo "building httpserver container"
	docker build -t jennykjr/httpserver:${tag} .

push: release
	echo "pushing jennykjr/httpserver"
	docker push jennykjr/httpserver:v1.0
