## Intro

Ifconfig-is is an IP lookup online service. Live demo: [https://ifconfig.is](https://ifconfig.is).

A fully worked service consists of 3 components:

1.  Backend API service ([https://github.com/ifconfig-is/api](https://github.com/ifconfig-is/api)):

    We use a GraphQL API to provide IP data. The data source is GeoLite2 from [MaxMind](https://www.maxmind.com).

2.  Frontend static resources ([https://github.com/ifconfig-is/web](https://github.com/ifconfig-is/web)):

    Static files: html, css, js.

3.  Dispatcher ([https://github.com/ifconfig-is/dispatcher](https://github.com/ifconfig-is/dispatcher)):

    The web service can be accessed from both browser and headless tool.
    We need send different responses based on user agent.

## Command Line Usage

```
$ curl ifconfig.is
1.2.3.4

$ curl ifconfig.is/json
{
  "Continent":  "Asia",
  "Country"  :  "Singapore",
  "Latitude" :  1.314000,
  "Longitude":  103.683900,
  "TimeZone" :  "Asia/Singapore",
  "IsEU"     :  false,
  "ASN"      :  14061,
  "ORG"      :  "DIGITALOCEAN-ASN"
}

$ curl ifconfig.is/json/www.google.com
{
  "Continent":  "North America",
  "Country"  :  "United States",
  "Latitude" :  37.751000,
  "Longitude":  -97.822000,
  "TimeZone" :  "America/Chicago",
  "IsEU"     :  false,
  "ASN"      :  15169,
  "ORG"      :  "GOOGLE"
}
```

## License

See the [LICENSE](https://github.com/i3h/ifconfig/blob/master/LICENSE.md) file for license rights and limitations (MIT).

# Acknowledgements

[mpolden/echoip](https://github.com/mpolden/echoip)

[oschwald/geoip2-golang](https://github.com/oschwald/geoip2-golang)

[MaxMind](https://www.maxmind.com)
