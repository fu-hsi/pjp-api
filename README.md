# PJP API
Polish Air Quality API (REST).

## Official API
No special requirements. Available only GET method.
```
http://api.gios.gov.pl/pjp-api/rest/station/findAll
http://api.gios.gov.pl/pjp-api/rest/station/sensors/{stationId}
http://api.gios.gov.pl/pjp-api/rest/data/getData/{sensorId}
http://api.gios.gov.pl/pjp-api/rest/aqindex/getIndex/{stationId}
```
More information: http://powietrze.gios.gov.pl/pjp/content/api.

### Measuring stations

**Request**
```
http://api.gios.gov.pl/pjp-api/rest/station/findAll
```
**Response**
```
[{
    "id": 14,
    "stationName": "Dzia³oszyn",
    "gegrLat": "50.972167",
    "gegrLon": "14.941319",
    "city": {
        "id": 192,
        "name": "Dzia³oszyn",
        "commune": {
            "communeName": "Bogatynia",
            "districtName": "zgorzelecki",
            "provinceName": "DOLNOŒL¥SKIE"
        }
    },
    "addressStreet": null
}]
```

### Sensors

**Request**
```
http://api.gios.gov.pl/pjp-api/rest/station/sensors/14
```

**Response**

```
[{
    "id": 92,
    "stationId": 14,
    "param": {
        "paramName": "py³ zawieszony PM10",
        "paramFormula": "PM10",
        "paramCode": "PM10",
        "idParam": 3
    }
},
{
    "id": 88,
    "stationId": 14,
    "param": {
        "paramName": "dwutlenek azotu",
        "paramFormula": "NO2",
        "paramCode": "NO2",
        "idParam": 6
    }
}]
```

### Measurements

**Request**
```
http://api.gios.gov.pl/pjp-api/rest/data/getData/92
```

**Response**

```
{
    "key": "PM10",
    "values": [
    {
        "date": "2017-03-28 11:00:00",
        "value": 30.3018
    },
    {
        "date": "2017-03-28 12:00:00",
        "value": 27.5946
    }]
}
```

### Air Quality Index

**Request**
```
http://api.gios.gov.pl/pjp-api/rest/aqindex/getIndex/52
```

**Response**

```
{
    "id": 52,
    "stCalcDate": "2017-03-28 12:00:00",
    "stIndexLevel": {
        "id": 2,
        "indexLevelName": "Umiarkowany"
    },
    "stSourceDataDate": "2017-03-28 12:00:00",
    "so2CalcDate": "2017-03-28 12:00:00",
    "so2IndexLevel": null,
    "so2SourceDataDate": "2017-03-28 12:00:00",
    "no2CalcDate": "2017-03-28 12:00:00",
    "no2IndexLevel": null,
    "no2SourceDataDate": "2017-03-28 12:00:00",
    "coCalcDate": "2017-03-28 12:00:00",
    "coIndexLevel": null,
    "coSourceDataDate": "2017-03-28 12:00:00",
    "pm10CalcDate": "2017-03-28 12:00:00",
    "pm10IndexLevel": null,
    "pm10SourceDataDate": "2017-03-28 12:00:00",
    "pm25CalcDate": "2017-03-28 12:00:00",
    "pm25IndexLevel": null,
    "pm25SourceDataDate": null,
    "o3CalcDate": "2017-03-28 12:00:00",
    "o3IndexLevel": null,
    "o3SourceDataDate": "2017-03-28 12:00:00",
    "c6h6CalcDate": "2017-03-28 12:00:00",
    "c6h6IndexLevel": null,
    "c6h6SourceDataDate": "2017-03-28 12:00:00"
}
```

## Demo
http://pjp.powietrze.lomza.pl/