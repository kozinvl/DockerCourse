Use Python 3.6.

Application:
Installation:
- install packets: pip install -r requirements.txt
- create "logs" directory near app.py file
- run app: python app.py (the app will start on port 5000)

The app has two endpoints:
- http://localhost:5000/     - display a counter
- http://localhost:5000/logs - display the logs of "/" endpoint invocation

It is important that application depends on a Redis database. The Redis instance has to be available by redis:6379.


2.1
You need to create a Docker image for the application and push it ( hits:h3 tag). Also, the application depends on a Redis instance.
So, you need to run it from an official image. You have to use custom networks for establishing connectivity between the application
and Redis

2.2
need to have a backup of Redis's data and application's logs