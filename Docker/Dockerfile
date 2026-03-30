FROM python:latest
WORKDIR /app
COPY . /app
RUN pip install -r src/requirements.txt
EXPOSE 6300
CMD ["python", "src/server.py"]