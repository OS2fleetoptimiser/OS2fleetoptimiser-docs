---
title: FleetComplete
layout: default
parent: Extractors
has_children: false
---
# FleetComplete

The FleetComplete extractor expects the connection key to be present in the env as a single string, like:

```
KEYS=keyToFleetComplete
```


Use the `docker-compose-extractor.yaml` file and define the functions you want to use in the extractor:

| function         | description |
|------------------| ----------- |
| set-starts       | loads and saves new locations |
| set-vehicles     | syncs the vehicles |
| set-roundtrips   | loads, aggregate and save roundtrips | 
| clean-roundtrips | deletes X (keep_data in DB) month old roundtrips |

The FleetComplete extractor has on the `set-vehicles` method, an additional `--exempt-locations` flag, 
which is set in the occasion that one wants to opt out on relying on location updates from the 
FleetComplete api. 

```
entrypoint: ["/bin/sh", "-c", "python -m fleetmanager.extractors.fleetcomplete set-starts && python -m fleetmanager.extractors.fleetcomplete set-vehicles && python -m fleetmanager.extractors.fleetcomplete set-roundtrips && python -m fleetmanager.extractors.fleetcomplete clean-roundtrips"]
```