FROM python:3.6

EXPOSE 5000
WORKDIR /flask
COPY app.py ./
COPY index.html templates/
RUN pip install flask
CMD ["python", "./app.py"]