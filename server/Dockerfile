FROM python:3.12-slim

WORKDIR /app

RUN mkdir -p /app/data && chmod 755 /app/data

RUN pip install --no-cache-dir "mem0ai[qdrant]" fastapi "uvicorn[standard]" anthropic "psycopg[pool]"

COPY main.py .

EXPOSE 8000
ENV PYTHONUNBUFFERED=1

CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
