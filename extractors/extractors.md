---
title: Extractors
layout: default
nav_order: 4
has_children: true
---

# Extractors
The extractors are an important part of FleetOptimiser, which asserts that data is synced from the fleetmanagement systems.
The extractor will synchronise available metadata with vehicles, and will delta load the latest trips. 
Trips will be aggregated from single GPS logs, to an aggregated format that will only contain coordinates of a saved start location, 
such that the system does not save sensitive information.


The amount of exposed metadata differ from system to system, so with some integrations there are more sanitation of data. 


All extractors expect the following env variables:

| env | description |
|-----|-------------|
| DB_NAME          | name of the database |
| DB_USER          | user of the database |
| DB_PASSWORD      | password of the user on the database |
| DB_URL           | host and port to the database |
| DB_SERVER        | dialect and driver |
| TRIP_DURATION | maximum duration of a roundtrip |
| MAX_DATE | first delta load date |
| DESCRIPTION_FIELDS | additional fields to save from APIs



