build:
	docker build ${DOCKER_BUILD_OPTS} ${DOCKER_BUILD_ARGS} -t "buluma/curl:${LATEST_RELEASE_VERSION}" -f Dockerfile .

multibuild:
	docker buildx build ${DOCKER_BUILD_OPTS} ${DOCKER_BUILD_ARGS} -t "buluma/curl:7.83.1" --platform=${DOCKER_MULTI_ARCH} -f Dockerfile . --push
	docker buildx imagetools create docker.io/buluma/curl:7.83.1 --tag buluma/curl:latest

lint:
	docker run --rm --privileged -v ${PWD}:/root/ projectatomic/dockerfile-lint dockerfile_lint -p -f Dockerfile

test:
	../../bin/container-structure-test test --image curl/curl:${LATEST_RELEASE_VERSION} --config "test-container.yml"
	docker run --rm curl/curl:${LATEST_RELEASE_VERSION} -S http://httpbin.org/get

push-registry:
	docker tag curl/curl:${LATEST_RELEASE_VERSION} buluma/curl:7.83.1
	docker push buluma/curl:7.83.1
	docker tag curl/curl:${LATEST_RELEASE_VERSION} buluma/curl:latest
	docker push buluma/curl:latest

scan:
	docker run --rm -v /var/run/docker.sock:/var/run/docker.sock -v /tmp:/root/.cache/ aquasec/trivy curl/curl:${LATEST_RELEASE_VERSION}
	curl -sSfL https://raw.githubusercontent.com/anchore/grype/main/install.sh | sh -s -- -b /usr/local/bin && grype curl/curl:${LATEST_RELEASE_VERSION}

clean:
	rm -Rf curl
	rm -Rf *.log
	rm -Rf anchore-reports
