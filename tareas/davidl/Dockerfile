FROM python:3

WORKDIR /usr/src

RUN apt update
RUN apt install -y git


RUN git clone "https://github.com/joaoventura/flask-static-site"

RUN pip3 install -r ./flask-static-site/requirements.txt

EXPOSE 8000

CMD [ "python", "./flask-static-site/site.py" ]
