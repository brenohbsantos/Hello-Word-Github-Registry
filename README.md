# Hello World

Hello world Docker image for testing :).
## Usage

### Build a Docker image

```shell
$ docker build . -t github-registry/hello-world .
Sending build context to Docker daemon  20.99kB
Step 1/7 : FROM python:3-alpine
 ---> a93594ce93e7
Step 2/7 : WORKDIR /usr/src/app
 ---> Running in 99c72d9f80c6
Removing intermediate container 99c72d9f80c6
 ---> ae6cf20413de
Step 3/7 : EXPOSE 8000
 ---> Running in 5feb111b3909
Removing intermediate container 5feb111b3909
 ---> b02c0d3d44cb
Step 4/7 : COPY requirements.txt .
 ---> f78be477ef4c
Step 5/7 : RUN pip install -qr requirements.txt
 ---> Running in 81044c1a701a
Removing intermediate container 81044c1a701a
 ---> f34572dbcf4a
Step 6/7 : COPY server.py .
 ---> 49185ab473c5
Step 7/7 : CMD ["python3", "./server.py"]
 ---> Running in 2446171f3946
Removing intermediate container 2446171f3946
 ---> 7d692d619894
Successfully built 7d692d619894
Successfully tagged github-registry/hello-world:latest
```

### Run it in Docker

Build the image first, then launch it using `docker run`.

```shell
$ docker run --rm -it -p 8000:8000 github-registry/hello-world
 * Serving Flask app "server" (lazy loading)
 * Environment: production
   WARNING: Do not use the development server in a production environment.
   Use a production WSGI server instead.
 * Debug mode: on
 * Running on http://0.0.0.0:8000/ (Press CTRL+C to quit)
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 131-286-398
```

## License

Licensed under Apache 2.0. Please see [License](LICENSE) for details.
