---
title: Developing
layout: default
nav_order: 3
---
# Developing

There are multiple ways of running FleetOptimiser in developing mode. 
One can decide to run none or multiple of services as containers.

Below follows an explanation of how to run the services without containerisation.

## Prerequisites 
- [npm](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm)
- [python ^3.10](https://www.python.org/downloads/) & pip
- [redis](https://redis.io/docs/latest/operate/oss_and_stack/install/install-redis/)
- [rabbitmq](https://www.rabbitmq.com/docs/download)


### Frontend
Go to `fleetoptimiser-frontend` and run 
```
/fleetoptimiser-frontend >>   npm install
```

to install all the necessary packages for running the FleetOptimiser frontend.

When installed, you'll be able to run the frontend in dev mode, by running the following command

```
/fleetoptimiser-frontend >>   npm run dev

> fleetoptimiser-frontend@0.1.0 dev
> next dev

  ▲ Next.js 14.2.14
  - Local:        http://localhost:3000
  - Experiments (use with caution):
    · esmExternals

 ✓ Starting...
 ✓ Ready in 5.2s
```

This sets the `node_env` as `development` asserting that no user authentication is needed. 

The frontend can now be accessed at localhost:3000.


### Backend API
It's recommended to run the backend and workers from a virtual environment to have all FleetOptimiser required packages
located in a single environment. Hence, we'll refer to `virtualenv` whenever python relevant code is executed.

Create venv and install necessary packages: 
```
/OS2fleetoptimiser >>    /path/to/python3.10 -m venv virtualenv
/OS2fleetoptimiser >>    source virtualenv/bin/activate
/OS2fleetoptimiser >>    pip install poetry==1.3.1
/OS2fleetoptimiser >>    poetry config virtualenvs.create false
/OS2fleetoptimiser >>    poetry install

Installing the current project: fleetmanager (1.0.0)
```

Now, we've successfully installed necessary packages and modules in FleetOptimiser. 
To run the backend api run the following command:


```
/OS2fleetoptimiser >>    uvicorn fleetmanager:api.app --port 3001 --host 0.0.0.0 --proxy-headers --root-path /api --workers 2
INFO:     Uvicorn running on http://0.0.0.0:3001 (Press CTRL+C to quit)
INFO:     Started parent process [29300]
INFO:     Started server process [29302]
INFO:     Waiting for application startup.
INFO:     Application startup complete.
INFO:     Started server process [29303]
INFO:     Waiting for application startup.
INFO:     Application startup complete.
```

Backend api can be reached on localhost:3001, API documentation will be shown if base path is visited with a browser.

### Celery worker
To have a worker running, which picks up simulation tasks as well as location precision tasks, we need to boot a worker with celery.


With the venv activated as shown in Backend API, run the following command to start a worker:
```
/OS2fleetoptimiser >>    celery -A fleetmanager.tasks.celery worker --pool threads
 -------------- celery@LAPTOP-john v5.4.0 (opalescent)
--- ***** -----
-- ******* ---- Linux-5.15.146.1-microsoft-standard-WSL2-x86_64-with-glibc2.31 2024-11-21 14:42:49
- *** --- * ---
- ** ---------- [config]
- ** ---------- .> app:         fleetmanager_0fd19aa5f2d348669935339d76e3b414:0x7f15eb141120
- ** ---------- .> transport:   amqp://guest:**@localhost:5672//
- ** ---------- .> results:     redis://localhost/
- *** --- * --- .> concurrency: 8 (thread)
-- ******* ---- .> task events: OFF (enable -E to monitor tasks in this worker)
--- ***** -----
 -------------- [queues]
                .> default          exchange=celery(direct) key=celery
```

As you can see the worker will post results to redis running on the localhost and expect 'brokerage' through localhost port 5672. 
Hence, we need to make sure that we have a locally running redis and rabbitmq on the expected ports; 6379 and 5672 respectively.

### Communication 
Make sure that the services uses the correct default ports for successful communication between them.

| from           | to          | default port localhost |
|----------------|-------------|------------------------|
| frontend       | backend | 3001                   |
| backend/celery | rabbitmq    | 5672 |
| backend/celery | redis | 6379 |

In development, it's the easiest to have redis and/or rabbitmq running as docker containers with a mapping to the localhost ports.

### Docker
Any of the services can also be run with docker/compose, which is exemplified in the `docker-compose-dev.yaml` file where the 
backend and worker is run containerised and one would run the frontend separately. Hence, the backend mapping to localhost:3001.

In that scenario, you would run 
```
docker-compose -f docker-compose-dev.yaml up -d
docker run -p 5672:5672 rabbitmq:4.0-management -d
docker run -p 6379:6379 redis -d
npm run dev
```

See [production](production.md) for environment variables for the backend. 

