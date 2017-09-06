REGISTRY = 080385600816.dkr.ecr.us-east-1.amazonaws.com
TAG = 0.0.26-0
LOGIN:=$(shell aws ecr get-login --no-include-email)
APP = tomcat9
all:
	container

container:
	docker build -t $(APP):$(TAG) .
	
push-container: container
	exec ${LOGIN}
	docker tag $(APP):$(TAG) ${REGISTRY}/$(APP):$(TAG)
	docker push ${REGISTRY}/$(APP):$(TAG)

clean:
	mvn clean
