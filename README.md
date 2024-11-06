# Full Tutorial: Setting Up Azure Sentinel with Real-Time Attack Visualization

This tutorial covers how to set up **Azure Sentinel** for real-time security monitoring with geographic visualization of attacks. This guide is ideal for beginners who want to explore the capabilities of a Security Information and Event Management (SIEM) solution.

## Tutorial Steps

### 1. Preview the Technical Steps 
- Overview of the objectives: create virtual machines (VMs), configure logs, and collect geolocation data for attack analysis.

### 2. Create an Azure Subscription 
- Go to [azure.com](https://azure.com) and, if necessary, create an account.
- Select or create a new subscription to start using Azure resources.

### 3. Create a Virtual Machine (VM) 
- In the Azure portal, go to **Virtual Machines** > **Create**.
- Choose the VM configuration, such as the operating system (Windows, in this case) and the region.
- Finish the creation and wait for the deployment.

### 4. Allow All Traffic Through the Firewall 
- In the VM settings menu, go to **Networking** > **Security Settings**.
- Configure the firewall to allow all traffic (Inbound and Outbound) to simulate external attacks.

### 5. Create a Log Analytics Workspace 
- Go to **Azure Sentinel** > **Log Analytics Workspace** and create a new workspace.
- This workspace will be used to store the logs and events captured by the VM and other resources.

### 6. Enable VM Log Collection in Security Center 
- Go to **Azure Security Center** and locate the VM you created.
- Enable log collection, including security logs and system events.

### 7. Connect Log Analytics Workspace to the VM 
- In the Azure portal, go to **Log Analytics Workspace** and add the VM as a connected resource.
- This will allow the VM to send log data directly to the workspace.

### 8. Configure Azure Sentinel 
- In the Log Analytics Workspace, enable **Azure Sentinel**.
- Sentinel will now be active and will begin collecting data from configured sources, such as the VM’s logs.

### 9. Log into the VM with Remote Desktop and Fail a Login 
- Using **Remote Desktop (RDP)**, attempt to connect to the VM.
- Intentionally trigger a login failure to simulate a possible attack or hacking attempt.

### 10. View Logs in the VM’s Event Viewer 
- After logging in, open the **Event Viewer** on the VM. - Check the generated logs, especially in **Windows Logs** > **Security**, where login failures are recorded.

### 11. Disable Windows Firewall on the VM 
- Go to **Windows Firewall** on the VM and disable it.
- This setting will allow test traffic to come in to simulate attacks.

### 12. Download a PowerShell Script 
- Download the PowerShell script provided in the tutorial. It will be used to get geolocation data from the attackers.

### 13. Get Geolocation.io API Key 
- Go to [Geolocation.io](https://geolocation.io) and create an account to generate an API key.
- This key will be used in the PowerShell script to get location data from the attacker IPs.

### 14. Run PowerShell Script to Get Attackers’ Geolocation Data 
- On the VM, open PowerShell and run the script with the Geolocation.io API key.
- The script will collect geolocation data for IPs attempting to access the VM.

### 15. Create Custom Log in Log Analytics Workspace 
- Go to **Log Analytics Workspace** and create a custom log to store the script data.
- This will allow you to capture and store IP geolocation data for visualization in Sentinel.

### 16. Extract Custom Fields from Logs 
- Use **Custom Logs** in Log Analytics to extract specific fields such as Latitude and Longitude.
- This will help you visually map the source of attacks in Azure Sentinel.

### 17. Test Field Extractions 
- Review the extracted custom fields and validate that the geolocation data is correct. - Perform tests to ensure that the data is being captured as expected.

### 18. Configure the Map in Sentinel with Latitude and Longitude (or Country)
- In **Azure Sentinel**, configure a map that uses the Latitude and Longitude fields from the custom logs.
- This map will show the location of the attacking IPs in real time.

### 19. Adjust the Size of Points on the Map 
- Customize the map to adjust the size of the attack points, making them easier to visualize.
- This makes it easier to identify the regions with the most activity.

### 20. Watching Attacks on the Map 
- Watch the visualizations on the map as different countries launch attacks: China, Taiwan, Philippines, Russia, and others.
- The map should display these attacks based on the geolocation data from the logs.


### 21. Final Check on the Map 
- Check the map to confirm that all attacks are being recorded and displayed correctly.
- Ensure that the configuration is working as expected.

### 22. Final Thoughts and Observations 
- Complete the analysis in **Azure Sentinel**, considering the observed patterns and the effectiveness of the configured detection rules.
- Review the process and the insights gained.
