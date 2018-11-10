FROM python:3.6

LABEL author="Kozin Vladyslav"
WORKDIR /.
COPY hits/app.py ./
COPY requirements.txt ./
RUN mkdir +chmod logs && pip install -r requirements.txt
EXPOSE 5000
CMD ["python", "./app.py"]


#docker build -t hw3 .
#docker tag hw3 vkozin/hits:h3
#docker push vkozin/hits:h3
#docker network create –driver=bridge volia
#docker run -itd –net=volia –rm -p 6379:6379 –name=redis redis
#docker run -itd –net=volia –rm -p 5000:5000 –name=hw3 vkozin/hits:h3