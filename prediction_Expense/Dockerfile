FROM python:3.11-slim-buster
WORKDIR /app
COPY . /app
RUN pip3 install --upgrade pip
RUN pip3 install -r requirements.txt --break-system-packages
EXPOSE 8080
CMD python3 ./app.py
