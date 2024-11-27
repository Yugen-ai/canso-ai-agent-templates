FROM --platform=linux/amd64 python:3.9.18-slim

WORKDIR /opt/ai-agent/

RUN mkdir src

COPY src ./src
COPY .env ./
COPY config.yaml ./config.yaml
COPY requirements.txt ./

RUN pip3 install --no-cache-dir -r requirements.txt

EXPOSE 8000

CMD ["python3", "src/main.py"]
