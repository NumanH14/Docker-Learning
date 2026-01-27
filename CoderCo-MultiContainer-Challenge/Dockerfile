FROM python:3.8-slim
WORKDIR /APP
COPY . .
RUN pip install flask redis
EXPOSE 5002
CMD ["python", "app.py"]
