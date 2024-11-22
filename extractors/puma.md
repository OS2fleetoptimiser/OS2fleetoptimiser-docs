---
title: Puma
layout: default
parent: Extractors
has_children: false
---
# Puma

PUMA connection requires VPN access, which details will not be explained here. 
In addition to VPN access, it's also required to have read access to the PUMA database. 

We use a load record path to make loading of trips more efficient. In order not to continuously load unused _old_ trips.

- `LOAD_RECORD_PATH` : path to a json mapping that stores load history
- `FORVALTNINGER` : list of forvaltninger to load trips from
- `PUMA_DRIVER` : the dialect of puma connection
- `PUMA_USER` : user on the puma connection
- `PUMA_URL` : url to the puma connection 
- `PUMA_NAME` : name of the puma connection
- `PUMA_PASSWORD` : password to the puma connection


Use the `docker-compose-extractor.yaml` file and define the functions you want to use in the extractor:

| function         | description |
|------------------| ----------- |
| set-starts       | loads and saves new locations |
| set-vehicles     | syncs the vehicles |
| set-roundtrips   | loads, aggregate and save roundtrips | 
| clean-roundtrips | deletes X (keep_data in DB) month old roundtrips |


```
entrypoint: ["/bin/sh", "-c", "python -m fleetmanager.extractors.puma set-starts && python -m fleetmanager.extractors.puma set-vehicles && python -m fleetmanager.extractors.puma set-roundtrips && python -m fleetmanager.extractors.puma clean-roundtrips"]
```

