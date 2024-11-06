# SIEM --Azure Sentinel Configuration and Real-Time Attack Monitoring Guide


This guide teaches you how to configure Azure Sentinel for security monitoring with real-time attack visualization, ideal for those new to SIEM solutions.

1. Configure Azure Sentinel in the Azure Portal
Go to the Azure Portal.
Navigate to Azure Sentinel and click Create to launch a new Sentinel instance.
Select or create a new Log Analytics Workspace. This workspace will store the logs and event data that Sentinel will use.

2. Connect Data Sources to Sentinel
On the Azure Sentinel dashboard, click Data connectors.
Connect the desired data sources, such as Microsoft 365 logs, Azure Active Directory, or external device logs.
Each data connector has a configuration guide; follow the instructions to integrate correctly.
Example: If you are configuring Microsoft Defender as a data source, select the connector and authorize the connection.

3. Configure Detection Rules
Go to the Analytics tab in the Azure Sentinel dashboard.
Add detection rules to monitor specific events. These rules define the types of suspicious activity to identify, such as unauthorized access attempts or repeated failed logins.
Select from pre-configured rules or create custom rules based on Kusto Query Language (KQL) queries to filter events.

4. Monitor and Visualize Security Alerts
Go to the Sentinel Overview dashboard, where you will see a threat map that shows the location of detected events and alerts.
View the real-time visualization of alerts to monitor suspicious activity and quickly identify any threats.

5. Configure Automated Incident Response Playbooks
From the Sentinel menu, go to Automation and configure Playbooks.
Playbooks are automated response flows that can be configured to perform specific actions, such as sending notifications, blocking an IP, or updating the status of an alert.
These flows are configured through Azure Logic Apps, allowing you to create automated incident responses.

6. Incident Investigation and Analysis
Go to the Incidents tab to see a list of incidents detected by Sentinel.
Click on an incident to see details, including the source, date, and actions taken.
Use the Investigate option to launch a deep dive analysis that visualizes the connections between events and helps you track the source and impact of the threat.

7. Dashboards and Reports
For a complete view, go to Workbooks and select from pre-configured dashboards or create a custom one.
Dashboards provide key metrics and visualizations of security data, allowing you to identify attack patterns and analyze the overall security of your organization.
