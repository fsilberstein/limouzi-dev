BASEREPO = fsilberstein
IMAGE = meetup-devops

.PHONY: build
build:
	CGO_ENABLED=0 GOOS=linux go build -i -o ./main -ldflags '-s' -installsuffix cgo main.go

.PHONY: test
test-unit:
	go test -v ./...

docker:
	docker build --no-cache -t $(BASEREPO)/$(IMAGE):latest . && \
	docker push $(BASEREPO)/$(IMAGE):latest