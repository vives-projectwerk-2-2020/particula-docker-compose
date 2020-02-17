# particula-docker-compose

# TODO 

- TTN Listener
- InfluxDB
- Grafana
- Backend
- Database
- Frontend

## To Run file
```
sudo docker-compose up -d
```

## On Linux

In your browser, go to : `localhost:3000`

## On Windows

Check your Docker_Toolbox machine IP and in your browser go to: `machineip:3000`

# InfluxDB

`https://docs.influxdata.com/influxdb/v1.7/tools/api/`

## Sending data with Postman

To push data to `particula-influxdb_data` with postman create following POST request:

```
POST http://localhost:8086/write?db=particula-influxdb_data&precision=s
```

body

```
sensors,sensor_id="sensor_01",location="lab2.80" temp=21.5 1581880318
```

## Viewing data with Postman

Following is an example to view all data within `sensors`:

```
GET http://localhost:8086/query?db=particula-influxdb_data&q=select * from sensors
```