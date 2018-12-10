---
layout: post
title: Getting Started With ELK Stack By Building Uptime Monitor.
path: "/posts/getting-started-with-elk-stack/"
draft: false
date: '2018-12-05T23:20:39.000Z'
description: |-
  What is ELK? long story short,ELK stand for Elasticsearch, Logstash, Kibana.
  Elasticsearch is a full-text, distributed NoSQL database.
  Logstash is a tool f...
tags:
  - ELK
  - Kibana
  - Elasticsearch
category: Devops
---

What is ELK? long story short,ELK stand for _**Elasticsearch**_, _**Logstash**_, _**Kibana**_.

_**[Elasticsearch](https://www.elastic.co/products/elasticsearch)**_ is a full-text, distributed NoSQL database.

[Logstash](https://www.elastic.co/products/logstash) is a tool for collecting, parsing, and storing logs for future use.

_**[Kibana](https://www.elastic.co/products/kibana)**_ is an open source analytics and visualization platform designed to work with Elasticsearch.

![](/content/images/2018/12/elk-flow.png)

There is one more tool, or actually tools i want to mention:

_[Beats](https://www.elastic.co/products/beats) a_ll kinds of shippers for all kinds of data (later on we are going to use [Heartbeat](https://www.elastic.co/products/beats/heartbeat) from the beats family).

ELK  stack can be overwhelming so i suggest we start with setup an environment and continue from that.

Quick setup with docker:

    git clone https://github.com/niradler/docker-elk
    cd docker-elk
    docker-compose -f "docker-compose.yml" up
    

lets see what we got:

    docker ps
    

![](/content/images/2018/12/ConEmu64_eWXUj2jGDo.png)

After docker compose finish we get 4 containers up, Kibana, Elasticsearch, Logstash and Heartbeat.

The All propose of the Elk stack is to store, analyze, and visualise data, so let's create data to work with, for that i'm going to use [Heartbeat](https://www.elastic.co/products/beats/heartbeat) (i choose this one only because it is simple to understand and very useful).

[_Heartbeat_](https://www.elastic.co/products/beats/heartbeat) monitor services for their availability with active probing.

in the heartbeat folder you can find the heartbeat.yml

![](/content/images/2018/12/carbon.png)

in this example i'm going to use heartbeat to call Elasticsearch root every 20s, google every 40s, and a random website every 40s, and of-course to report the result to Elasticsearch.

now let's open Kibana [http://localhost:5601](http://localhost:5601) and go to the management tab, choose [Index Patterns](http://localhost:5601/app/kibana#/management/kibana/indices/) and enter the index: heartbeat-\* , press next and choose timestamp.

now we can go to the discover tab and get amazed.

![](/content/images/2018/12/chrome_7cI8c6c3Cx-1.png)

Notes:

*   press the options button and turn on query features.
*   press the auto refresh button and configure it to keep update the data.
*   you can choose the field to show by hover them in the side menu and press add.
*   you can search with  monitor.status:up.

let's move on to the [Visualize](http://localhost:5601/app/kibana#/visualize) tab, press the plus button and choose pie, on the left choose the index we created earlier, now lets visualize the statuses we get from heartbeat, press **Split Slices** and fill:

*   Aggregation -> Terms
*   Field -> monitor.status

press the play button and you get:

![](/content/images/2018/12/chrome_ShFDUSJowO.png)

you can hover it to see the count, when you satisfied with the result press the save button on the top and enter a name for the chart.

Notes and resources:

*   watch this official elastic videos: [Elasticsearch](https://www.elastic.co/webinars/getting-started-elasticsearch), [Kibana](https://www.elastic.co/webinars/getting-started-kibana), [Logstash](https://www.elastic.co/webinars/getting-started-logstash)
*   logz.io have lots of good examples and they are free to experiment up to 3gb.
*   to experiment with Elasticsearch you can use the Dev Tools in Kibana.
    
