FROM python:3.8-slim AS build

WORKDIR /app

COPY . .

RUN apt-get update && apt-get install -y \
    gcc \
    python3-dev \
    libmariadb-dev \
    pkg-config

COPY . .

RUN pip install flask mysqlclient

# Production stage

FROM python:3.8-slim

WORKDIR /app

COPY --from=build /app /app

EXPOSE 5002

CMD ["python", "app.py"]

