# Telemetry Dashboard Generator

The dashboard can display and compare data collected with Telemetry on weekly basis. The dashboard picks up
a configuration file, given as a GET parameter, that contains a description of the data format, e.g:

```javascript
{
  "sort-options": {
    "values": ["Impact", "Popularity", "Median (ms)", "75% (ms)"],
    "selected": "Impact"
  },
  "filter-options": [
    {"id": "Application",
     "values": ["Firefox", "Fennec"],
     "selected": "Firefox"},
    {"id": "Platform",
     "values": ["WINNT", "Linux", "Darwin", "Android"],
     "selected": "WINNT"},
    {"id": "Measure",
     "values": ["startup_MS", "shutdown_MS"],
     "selected": "startup_MS"},
    {"id": "Limit",
     "values": [10, 25, 100],
     "selected": 10}
  ],
  "title": ["Telemetry Add-on Performance", "Bootstrap add-on start up and shut down times"],
  "main-header": "Name",
  "header": ["Application", "Platform", "Addon ID", "Version", "Name", "Measure",
             "Sessions", "Popularity", "Impact", "Median (ms)", "75% (ms)", "95% (ms)"],
  "url-prefix": "https://s3-us-west-2.amazonaws.com/telemetry-public-analysis/addon_perf/data/weekly_addons"
}
```