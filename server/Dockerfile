FROM python:3.12.3-slim-bullseye

WORKDIR /usr/src/app

RUN pip install "poetry==1.8.2"

COPY pyproject.toml poetry.lock ./

RUN poetry install --without dev

COPY . ./

EXPOSE 8000

CMD ["poetry", "run", "uvicorn", "--host", "0.0.0.0", "--port", "8000", "wsgi:app"]
