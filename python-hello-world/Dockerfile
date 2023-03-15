## Desde donde lo vamos a Descargar la imagen Base
FROM python:3.6

LABEL maintainer="D.L"

COPY . /app

WORKDIR /app

RUN pip install -r requirements.txt

EXPOSE 8080

ENTRYPOINT ["python"]

CMD ["src/server.py"]