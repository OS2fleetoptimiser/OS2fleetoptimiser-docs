---
title: Clevertrack
layout: default
parent: Extractors
has_children: false
---
# Clevertrack

Clevertrack uses a method of patching already read trips. 
If one does not patch you would continuously have to load already _known_ trips, because it's not possible to query
based off of vehicle id. Hence, you have to define a date from which you want to load trips, and manage patching.

The connection requires a `TOKEN` environment which is a classic uid format. 
In addition, you should provide a pickle path to;
- `CAR_TRIPS_IDS` : path to a pickle that stores mapping between vehicle ids and patched trips
- `PATCHED_IDS` : path to a pickle that stores record of patched trips


Use the `docker-compose-extractor.yaml` file and define the functions you want to use in the extractor:

| function         | description                          |
|------------------|--------------------------------------|
| set-vehicles     | syncs the vehicles                   |
| set-roundtrips   | loads, aggregate and save roundtrips | 
| patch-roundtrips | patches read trips on the connection |


```
["/bin/sh", "-c", "python -m fleetmanager.extractors.clevertrack set-vehicles && python -m fleetmanager.extractors.clevertrack set-roundtrips && python -m fleetmanager.extractors.clevertrack patch-roundtrips"]
```
