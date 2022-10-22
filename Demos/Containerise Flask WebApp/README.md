`Flask is a web application framework written in Python.`

We will build and run a basic Flask webapp using this steps:

Via Dockerfile
- Install required dependencies
- Install and configure the web server
- Start web server

Build the container image
`docker build -t flask-webapp .`

Run the container
`docker run -p 5000:5000 flask-webapp`

Browse to `http://localhost:5000`

Clean up
`docker ps -a`
`docker stop [container]`
`docker rm [container]`
`docker rmi [image]`


References:
https://flask.palletsprojects.com/en/2.2.x/
https://pythonbasics.org/what-is-flask-python/