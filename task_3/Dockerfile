FROM python:3.6

LABEL author="Kozin Vladyslav"
WORKDIR /app
COPY hits/app.py ./
COPY requirements.txt ./
RUN mkdir +chmod logs && pip install -r requirements.txt 
EXPOSE 5000
CMD ["python", "./app.py"]