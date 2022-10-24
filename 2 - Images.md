**Create an image**

**Dockerfile layers**
- OS
- Update repo
- Install dependencies
- Copy source code to host folder
- Specify entrypoint

**Dockerfile format**
``` 
Instruction     Argument 
```

**Example Flask app**
> nano Dockerfile
```sh
FROM Ubuntu

RUN apt-get update
RUN apt-get install python

RUN pip install flask
RUN pip install flask-mysql

COPY . /opt/source-code

ENTRYPOINT FLASK_APP=/opt/source-code/app.py flask run
```

**Build Dockerfile**
```sh
docker build Dockerfile -t [image-name]/[tag]
*where -t is to add a tag
```

**Upload image in public Docker hub registry**
```sh
docker push [image-name]/[tag]
```