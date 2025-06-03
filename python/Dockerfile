FROM python:3.11-buster

WORKDIR /app

COPY requirements.txt .

RUN pip install --no-cache-dir -r requirements.txt

COPY . .

EXPOSE 8080

CMD ["uvicorn", "spaceship.main:app", "--host", "0.0.0.0", "--port", "8080"]
