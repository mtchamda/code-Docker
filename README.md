# NodeJS Application with Loki, Grafana, and Promtail
This is a sample project that demonstrates how to collect and visualize logs from a NodeJS application using Loki, Grafana, and Promtail. The project includes a NodeJS application that logs to standard output, a Promtail container that scrapes the logs and forwards them to Loki, a Loki container that indexes and stores the logs, and a Grafana container that provides a dashboard for visualizing the logs.

Launching the Application
To launch the application, follow these steps:

Install Docker and Docker Compose if they are not already installed.
Clone this repository to your local machine.
Change to the project directory: cd nodejs-loki-grafana-promtail
Build the NodeJS application Docker image: docker build -t nodejs-app .
Start the application with Docker Compose: docker-compose up -d
Access the Grafana dashboard at http://localhost:3000
Configuring Grafana
Once the application is running, you can configure Grafana to display the logs from the NodeJS application.

Log in to the Grafana dashboard at http://localhost:3000.
Click on "Add data source" and select "Loki" as the data source type.
Enter http://loki:3100 as the URL for the Loki data source.
Click on "Save and Test" to test the connection to Loki.
Create a new dashboard and add a new panel.
Choose "Loki" as the data source for the panel.
Enter a query to retrieve the logs from the NodeJS application, such as {app="nodejs-app"}.
Save the panel and view the logs.
Stopping the Application
To stop the application, use the following command:

bash
Copy code
docker-compose down
This will stop and remove all of the Docker containers for the application.

Conclusion
This project demonstrates how to collect and visualize logs from a NodeJS application using Loki, Grafana, and Promtail. With this setup, you can easily monitor your NodeJS application logs and quickly identify issues.
