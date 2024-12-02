#python
from ubuntu:18.04

RUN apt update 
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y -q python-all python-pip

COPY requirements.txt /tmp/requirements.txt
RUN pip install -r /tmp/requirements.txt
COPY app.py /opt/webapp/
WORKDIR /otp/webapp
EXPOSE 5000
CMD ["python", "app.py"]
