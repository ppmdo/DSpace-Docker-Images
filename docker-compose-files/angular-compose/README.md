## Running Standalone DSpace Angular connected to an External REST service

## 1. Pre-requisites
- [Setting Up Docker for DSpace](../../documentation/tutorialSetup.md)

- Set the environment variable DPROJ to a shorthand version of the version of DSpace you are running (this needs to be distinct for each database schema version). Docker will name the network, images, and persistent volumes with this value.  This will allow you to host multiple DSpace configurations through Docker.

```
export DPROJ=d7
```

## 2. Using Docker Compose

- cd to the **dspace-compose** directory

Run Docker compose

```
docker-compose -p $DPROJ up -d
```

This will start 1 container: Node - Angular.

## 3. Open DSpace in a Browser
- DSpace 7 UI: [http://localhost:3000](http://localhost:3000)

## 4. Stopping DSpace
To stop DSpace, the following command can be run.  The image will be retained in a stopped state.
```
docker-compose -p $DPROJ stop
```

You can destroy the images with the following command.  This command will be necessary to run if you change the compose file that you are using.

```
docker-compose -p $DPROJ down
```


## 6. Restarting DSpace
_When DSpace is restarted, the contents of your volumes will be restored_

```
docker-compose -p $DPROJ up -d
```

## 7. Destroying Docker Resources

```
docker-compose -p $DPROJ down
```
