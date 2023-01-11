# DotNET Microservice Monitoring

## Prerequisites

- [Docker](https://docs.docker.com/get-docker/) installed and running.

- A running Docker instance of [DotNET Microservice Kong/PostgreSQL Version](https://github.com/Brad-IW/dotnet-microservice-alternate)

## Installation Guide

1. Clone this repo and extract the files.
2. Open a terminal and navigate to the dotnet-microservice-alternate folder.
3. Run `docker-compose up`

    Once the compose file has finished its start up procedure the Grafana will be available at `http://localhost:3000/`. If you are trying to access the API from another device replace `localhost` with the servers ip address or domain name. 

4. Navigate to `http://localhost:3000/` in a web browser of your choice to reach the login page.
5. Login using the default admin login 

    Username: admin

    Password: admin

6. Enter a new, secure password into the new password fields and click submit.
7. Click the Grafana icon on the top left of the left navbar.
8. In the center of the page, click the "Add your first data source" button
9. Click Prometheus

    In the URL field, add `http://prometheus:9090`

10. Click Save & Test at the bottom of the page. This should show a popup saying "Data source is working."
11. On the left navbar, click the Dashboard button (The 4 squares), then press Import
12. Click upload JSON file, then select the `API Dashboard.json` provided within the repo.
13. Finally press import.

    The dashboard should now be showing information about requests and responses made by the API. 