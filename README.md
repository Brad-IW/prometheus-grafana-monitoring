# DotNET Microservice Monitoring

## Prerequisites

- [Docker](https://docs.docker.com/get-docker/) installed and running.

- A running Docker instance of [DotNET Microservice Kong/PostgreSQL Version](https://github.com/Brad-IW/dotnet-microservice-alternate)

## Installation Guide



open grafana page
login with admin/admin
set password

click add your first data source
click prometheus
set url to http://prometheus:9090/
click save and test
click grafana logo in top left

click 4 squares button
either: create new dashboard
or:
    import
    copy json from API Dashboard.json
    paste into import via panel json
    click load
    click import 

    

add dashboard (pull from api dashboard.json)
