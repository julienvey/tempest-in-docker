# Docker container running tempest test suite for OpenStack

## Quick start: Use container from DockerHub

You need two configuration files to run tempest

* tempest.conf  : Global configuration file
* accounts.yaml : credentials to test your OpenStack cloud

Run your docker container
```
docker run -v /local/path/to/tempest.conf:/etc/tempest/tempest.conf \
           -v /local/path/to/accounts.yaml:/etc/tempest/accounts.yaml
           julienvey/tempest-in-docker
```
This will run all tempest test on your OpenStack cloud

To run a subset of tests, e.g tempest.api.compute

```
docker run -v /local/path/to/tempest.conf:/etc/tempest/tempest.conf \
           -v /local/path/to/accounts.yaml:/etc/tempest/accounts.yaml
           julienvey/tempest-in-docker tempest.api.compute
```

## Do It Yourself

### Build

Build your container with your own image name

```
docker build -t <username>/tempest-in-docker .
```

### Run tempest test suite

Same as section above but with your own image name
