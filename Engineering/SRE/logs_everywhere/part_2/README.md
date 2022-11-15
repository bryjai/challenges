# Bryj.ai DevOps/SRE Challenge - Part 2 - Enriching Logs

Your second task is to enrich the logs by adding a field that contains the country ISO code from where the log just came
from.

In order to know the country ISO code for a given IP, you can use the GeoLite2 database.

You can use this [Docker image](https://hub.docker.com/r/observabilitystack/geoip-api) containing the GeoLite2 database
and an API service to recover information about an IP:

Now you can run the GeoLite2 API by running a docker container as follows:

```shell
$ docker run -p 8080:8080 ghcr.io/observabilitystack/geoip-api:latest-native
```

You will be able to request a local API running on the port 3000 and you can request it as follows:

`GET http://localhost:8080/169.43.192.15`

Expected response:

```json
{
  "country": "CH",
  "latitude": "47.1449",
  "longitude": "8.1551",
  "continent": "EU",
  "timezone": "Europe/Zurich"
}
```

Processing the log file should now output a JSON with the following format:

```json
{
  "logs": [
    {
      "type": "https",
      "date": "2019-08-30",
      "source_ip": "224.176.175.199",
      "response_time": "476",
      "target_url": "example.com/session",
      "http_code": "200",
      "iso_code": ""
    },
    {
      "type": "https",
      "date": "2019-08-29",
      "source_ip": "169.43.192.15",
      "response_time": "325",
      "target_url": "example.com/logs",
      "http_code": "200",
      "iso_code": "CH"
    },
    ...
  ]
}
```

Please be aware that the GeoLite2 API might not be able to return the country code for some IPs.
On that case, you can just consider it as _empty_.

You can go to the Part 3 now.
