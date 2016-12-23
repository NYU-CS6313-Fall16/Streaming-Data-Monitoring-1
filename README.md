# streaming-data-visualization
Streaming real time data using Accern API which consist of data captured from 20 million public websites or social medias. Basically, the unit is article. Similar articles can be grouped into stories which is about events happened on companies. The impact of the event is shown via an impact score representing the chance that an event may impact a company’s stock price by 1% at the end of trading day. 

First, we want to visualize the articles using dots with opacity 0.5. Now we look for highly dense area over the timeline which indicates there are a number of articles for that company in a short period of time. This might indicate some major episode of events happening at the company. Sentiment of article describes if the article was written positively or negatively by the author. It ranges from -1 to 1. So after indentifying an event we use a line chart to visualize the sentiment for that highly dense area of articles, to check if episode is having negative or positive sentiment.

# Tools and components used (recommended) to setup the visualization
  1.  Python 
      Version: 2.7.12
      Download Link: https://www.python.org/downloads/release/python-2712/
  2.  PyCharm Community Edition 2016.2.3 (By IntelliJ)
      JRE: 1.8.0_05-b13 amd64
      JVM: Java HotSpot(TM) 64-Bit Server VM by Oracle Corporation
      Download Link: https://www.jetbrains.com/pycharm/download/
  3.  Elasticsearch Database store
      Version: 5.0.2
      Download Link: https://www.elastic.co/downloads/elasticsearch
      Note: Elasticsearch will be installed locally and will use port 9200 i.e. (http://localhost:9200/)
      
# Steps for installing Python Packages and Modules
  1.  Install pip (Note: Python 2.7.9+ and 3.4+ comes with pip installed)
      Install instruction: Download and run 'get-pip.py' (https://bootstrap.pypa.io/get-pip.py)
      Reference: https://pip.pypa.io/en/stable/installing/#do-i-need-to-install-pip
  2.  Run command prompt/ terminal and execute following commands:
  
        1.  pip install flask
        2.  pip install flask_socketio
        3.  pip install flask_restful
        4.  pip install elasticsearch
        5.  pip install eventlet

# Steps for creating an index in elasticsearch
  1.  Start Python 2.7.12 console
  2.  Run the following commands:
  
      1.  from elasticsearch import Elasticsearch, RequestsHttpConnection
      2.  es = Elasticsearch(
             ['localhost:9200'],
             connection_class=RequestsHttpConnection
          )
      3.  es.indices.create(index='articles')
     
# Steps for starting the Visualization
  1.  Clone this project in PyCharm
  2.  Goto 'Streaming-Data-Monitoring-1 -> Backend -> app.py' in the project directory
  3.  Right Click and run app.py (Note: This will run the Flask Server for the Visualization, it may take few seconds so wait untill its running then goto step 4)
  4.  Goto 'Streaming-Data-Monitoring-1 -> Backend -> iviz.py' in the project directory
  5.  Right Click and run iviz.py
  6.  Start web browser and start link: http://127.0.0.1:5000/
(Note: Since the backend will start getting the data using ACCERN API, it will take some time to fill the main view depending on how fast ACCERN API provides the article data)
      

 
