# DotNET Microservice Monitoring

## Prerequisites

- [Docker](https://docs.docker.com/get-docker/) installed and running.

- A running Docker instance of [DotNET Microservice Kong/PostgreSQL Version](https://github.com/Brad-IW/dotnet-microservice-alternate)

## Installation Guide

1. Clone this repo and extract the files.
2. Open a terminal and navigate to the prometheus-grafana-monitoring folder.
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
13. Under Prometheus, select the data source we created in the previous steps.
13. Finally press import.

    The dashboard should now be showing information about requests and responses made by the API. Top left shows the number of responses for each status code, bottom left shows the total number of requests, and the right shows the time taken for each request.

## Test Plan

To test the dashboard we need to give prometheus some data. To accomplish this we will start up a new instance of the [DotNET Microservice Kong/PostgreSQL Version](https://github.com/Brad-IW/dotnet-microservice-alternate). 

1. Ensure both the microservice and monitoring services are running.
2. Make 5 requests to `http://localhost:80/api/users`, then check the Grafana dashboard.
    The dashboard should show that 5 requests were made in total, 5 200 responses were made in the response code summary.
3. Make 4 requests to `http://localhost:80.api/users/1234`, then check the Grafana dashboard.
    The dashboard should now show 9 total requests, and 5 200 responses and 4 400 respones.
