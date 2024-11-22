---
title: Gamfleet
layout: default
parent: Extractors
has_children: false
---
# Gamfleet

You must modify the urls in the Gamfleet extractor code in order to point to the correct endpoints.

To make the load more effective, we use a `LOAD_RECORD_PATH` to store load history of each vehicle. 
This asserts that we don't load _old_ unusable trips. 

- `LOAD_RECORD_PATH` : path to json history (optional)
- `KEY` : key to the Gamfleet API

Use the `docker-compose-extractor.yaml` file and define the functions you want to use in the extractor:

| function         | description |
|------------------| ----------- |
| set-starts       | loads and saves new locations |
| set-vehicles     | syncs the vehicles |
| set-roundtrips   | loads, aggregate and save roundtrips | 
| clean-roundtrips | deletes X (keep_data in DB) month old roundtrips |



```
entrypoint: ["/bin/sh", "-c", "python -m fleetmanager.extractors.gamfleet set-starts && python -m fleetmanager.extractors.gamfleet set-vehicles && python -m fleetmanager.extractors.gamfleet set-roundtrips && python -m fleetmanager.extractors.gamfleet clean-roundtrips"]
```