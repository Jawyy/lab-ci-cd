FROM python:3.10-alpine3.21
LABEL MANTAINER="Vitor Freitas"

WORKDIR /app

COPY . /app

# O 'apk upgrade' foi adicionado aqui para corrigir as vulnerabilidades do Alpine
RUN apk upgrade --no-cache \
    && apk add --no-cache curl \
    && pip install --trusted-host pypi.python.org -r requirements.txt

EXPOSE 8000

CMD ["gunicorn", "--bind", "0.0.0.0:8000", "app:app"]