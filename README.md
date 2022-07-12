# Instructions

Generate an asciidoc file for the example metrics endpoint response in sample_metrics.pef
For grouping purposes, a csv file with metric prefixes and the group title text to use is expected. For example:

```bash
go run ./prometheus_format.go -f sample_metrics.pef -c format_tables.csv > generated_metrics.adoc
```

To make it easier to keep any generated docs up to date, you may want to add a job to your CI that runs your service, scrapes metrics, generates the doc and then does a `git diff` to ensure the checked in doc is up to date.
For example:
```
curl http://myservice/metrics > /tmp/metrics.pef
go run ./prometheus_format.go -f /tmp/metrics.pef -c format_tables.csv > generated_metrics.adoc
git diff --exit-code
```

# Contributing

Feel free to open a PR with any suggested changes or features.