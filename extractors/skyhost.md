---
title: SkyHost
layout: default
parent: Extractors
has_children: false
---
# SkyHost 

First version extracts data through a SOAP API. The environment must contain variable `KEYS` with value string that evaluates to list of strings e.g.

```
KEYS="['firstKey', 'secondKey']"
```

Use the `docker-compose-extractor.yaml` file and define the entrypoints function you want to use

| function | description |
| -------- | ----------- |
| set-trackers | syncs the vehicles |
| set-roundtrips | loads, aggregate and save roundtrips | 
| clean-roundtrips | deletes X (keep_data in DB) month old roundtrips |

````
entrypoint: ["/bin/sh", "-c", "python -m fleetmanager.extractors.skyhost set-trackers && python -m fleetmanager.extractors.skyhost set-roundtrips && python -m fleetmanager.extractors.skyhost clean-roundtrips"]
````


# SkyHost V2

Second version uses the rest api, and uses env variables `ACCOUNT_IDS` and `API_KEYS` as a comma-separated list.
Each connection has exactly one account id and one api key. E.g.

```
ACCOUNT_IDS="accountId#1,accountId#2"
API_KEYS="apiKey#1,apiKey#2"
```

Use the `docker-compose-extractor.yaml` file and define the functions you want to use in the extractor:

| function           | description |
|--------------------| ----------- |
| set-allowed-starts | loads and saves new locations |
| set-trackers       | syncs the vehicles |
| set-roundtrips     | loads, aggregate and save roundtrips | 
| clean-roundtrips   | deletes X (keep_data in DB) month old roundtrips |


````
entrypoint: ["/bin/sh", "-c", "python -m fleetmanager.extractors.skyhost set-allowed-starts && python -m fleetmanager.extractors.skyhost set-trackers && python -m fleetmanager.extractors.skyhost set-roundtrips && python -m fleetmanager.extractors.skyhost clean-roundtrips"]
````

