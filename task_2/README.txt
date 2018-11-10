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