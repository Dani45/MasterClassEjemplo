# python-hello-world

Basic Python Flask app in Docker which prints the hostname and IP of the container

A nice and simple Python Flask application, which serves a greeting over HTTP.

To build a Docker image:

    docker build -t python-hello-world .

Then, to run:

    docker run --network=host python-hello-world

The app will respond on <http://localhost:8000> :

    $ curl localhost:8000
    Hello World!

If you want to deploy it to a registry (e.g. this is how I publish it to my quay.io account):

    docker login quay.io

    docker tag python-hello-world quay.io/tdonohue/python-hello-world:latest

    docker push quay.io/tdonohue/python-hello-world:latest

Verify the running container
Verify by checking the container ip and hostname (ID):

$ docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' my-container
172.17.0.2
$ docker inspect -f '{{ .Config.Hostname }}' my-container
6095273a4e9b