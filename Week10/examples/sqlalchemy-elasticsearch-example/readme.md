# SQLAlchemy, Flask and Elasticserach
This code is an example on how to connect Elasticsearch with SQLAlchemy
using event hooks.

When the Entry model is inserted or updated, it is indexed in Elasticsearch.

Then we have a route /api/search which uses Elasticsearch for searching for
entries.

## Install
For this code to work you must have a running Elasticsearch running
on the default port


    virtualenv .
    source bin/activate
    pip install -r requirements.txt

    python manage debug

## Add a new post
    
    curl -H "Content-Type: application/json" -d '{"title":"my stuff","content":"haha"}' http://localhost:5000/api/entries

## Curl a search

    curl -H "Content-Type: application/json" -d '{"search": "stuff"}' http://localhost:5000/api/search

