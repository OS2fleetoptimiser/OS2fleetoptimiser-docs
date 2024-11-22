---
title: MileageBook
layout: default
parent: Extractors
has_children: false
---
# MileageBook

The MileageBook extractor expects the connection key as environment variable:

```
KEY=apiKey
```


Use the `docker-compose-extractor.yaml` file and define the functions you want to use in the extractor:

| function         | description |
|------------------| ----------- |
| set-starts       | loads and saves new locations |
| set-vehicles     | syncs the vehicles |
| set-roundtrips   | loads, aggregate and save roundtrips | 
| clean-roundtrips | deletes X (keep_data in DB) month old roundtrips |


```
entrypoint: ["/bin/sh", "-c", "python -m fleetmanager.extractors.fleetcomplete set-starts && python -m fleetmanager.extractors.fleetcomplete set-vehicles && python -m fleetmanager.extractors.fleetcomplete set-roundtrips && python -m fleetmanager.extractors.fleetcomplete clean-roundtrips"]
```
