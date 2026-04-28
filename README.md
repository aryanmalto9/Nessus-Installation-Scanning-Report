# Nessus-Installation-Scanning-Report

The Nessus Installation & Scanning Report

BY: S Aryan Malto
DATE: 28-04-2026

Nessus is a powerful tool from Tenable that can scan networks, operating systems, databases and applications for vulnerabilities.
It provides detailed reports on security weaknesses and prioritizes them based on their severity.
It scans and looks for bad configuration, missing patches and CVEs (Common Vulnerabilities and Exposures) and is often used in security assessments and penetration testing.
Nessus is compatible with many platforms and operating systems, including:
•	Linux
•	Debian
•	Fedora
•	FreeBSD
•	MacOS
•	Red Hat
•	SUSE
•	Windows and Windows Server
Nessus offers two paid tiers, Professional and Expert, which come with extra features and capabilities, as well as a free Essentials version.
Nessus Essentials: This free version of Nessus is intended for educators, students, and individuals. You can use this tool to scan up to 16 private IP addresses.
Nessus Professional: This edition of Nessus is aimed at consultants, penetration testers and small to medium businesses. Nessus Professional offers unlimited vulnerability scanning of IT infrastructures with no restrictions on the number of IP addresses you can assess. The cost for a one-year license is $3990 USD.
Nessus Expert: This version of Nessus, which focuses on web application security, is also recommended for consultants, penetration testers, and developers. Nessus Expert allows you to extend the protection of your IT assets, covering web applications and cloud infrastructure, and gives you a clear view of your attack surface. The cost for a one-year license is $5990 USD.
How to Install Nessus on Kali Linux
This section will guide you through the process of downloading, installing and running Nessus Essentials on Kali Linux. Nessus does not come pre-installed in Kali and you have to download it from the Nessus website.
Download Nessus
To download Nessus, visit the download page and select the Linux-Debian-amd64.
Then select “Download” to download the file to Kali. Alternatively, you can use the command curlto download the file or download and install Nessus as a Docker image.
Installing Nessus
To install Nessus, simply enter the following command in the terminal, making sure you are in the same folder as the downloaded file:
sudo dpkg -i <File>
To start installing the plugins required before using Nessus, enter the following command at the command line:
sudo systemctl start nessusd.service
After starting the service, go to https://kali:8834/ in your browser to access and set up Nessus.
When you try to access the URL, a warning message will appear. Click on “Advanced…” and select “Accept the Risk and Continue.”
A Nessus welcome screen will then appear. Click “Continue” to proceed.
Select “Register for Nessus Essentials” on the next screen and click “Continue.”
On the next screen, enter your name and email address and click “Register” to continue.
On the next screen, enter your name and email address and click “Register” to continue.
 
On the next screen, you need to create a Nessus admin account, which will be used to log into Nessus.
 
Nessus will now start downloading the plugins.
 
Once the process is complete, you will be taken to the Nessus dashboard.
From here, Nessus will start setting up the plugins, which will take some time to complete. So grab a coffee and relax while Nessus does his thing.
 

Launch Nessus
To start Nessus, use the command:
sudo systemctl start nessusd. service
and then open https ://kali:8834/ in your browser.
You will need to log in with the details you set up earlier.
 



Once you’re logged in, you can start using Nessus.

 

Once you are done using Nessus, you can stop the service with the command:
sudo systemctl stop nessusd.service
Later in this guide, we’ll show you how to use Nessus in Kali.

After the installation is complete, Nessus will automatically open your default browser to complete the initial configuration at http://localhost:8834/WelcomeToNessus-Install/welcome .
This configuration must be completed before you can start using Nessus. To get started, click “Connect via SSL.”
 
Will a message about insecure connection appear? just ignore it and move on.
 










On the next screen, click “Continue” to start the configuration.
 
Select “Register for Nessus Essentials” and click “Continue.”  
On the next screen, enter your name and email address and click “Register” to receive an activation code.
 
Your activation code will appear on the next screen. Copy and save this code somewhere safe. Then click “Continue.”
 
You will then need to create an account to use Nessus. Enter a username and password and click “Submit.”
 
Nessus will now start downloading the necessary plugins, which will take a few minutes to complete.
 
You will then be taken to the Nessus interface, where the plugins will begin to be configured. This will take some time, so be patient and do not close the window or interrupt the process.
Once the configuration is complete, you’ll be ready to start scanning.
 



After starting the Nessus service, go to your browser and enter the address https://localhost:8834 . Enter the login information you created earlier and click “Sign In.”
Press enter or click to view image in full size
 
Once logged in, you can start scanning.
Run Nessus
Now we’ll show you how to use Nessus in Kali to perform a scan against a target within your network. But first, let’s briefly describe some of the key sections of the Nessus Essentials interface.
Press enter or click to view image in full size
 
•	My Scans: Displays and manages scheduled and startup scans. You can import results, create scan folders or start scans.
•	Settings: Check Nessus version details and plugin information, configure plugin updates, permissions, proxies, SMTP servers and more.
•	Policies: Create custom templates that control scan actions and plugin behaviors.
•	Plugin Rules: Customize how plugins work during scans.
•	Terrascan: Terrascan checks infrastructure code for security issues.
•	Notifications and Account: Manage account settings and scan notifications.
Nessus scan
Let’s start scanning our target. The first step is to click “Create a new scan.”
 
From here, we have the option to select a scan template. These are predefined templates for host discovery, basic network scans, web application testing, malware detection, and more.
For our demonstration, we will select “Basic Network Scan.”
 
After selecting “Basic Network Scan,” you need to configure some basic settings before starting the scan. We won’t cover all available settings here, but we’ll highlight the most important ones to help you get started.
The first setting you need to update is under Basic-General. Here you will enter the information about the target you want to scan by setting the name, description and IP address.

 
The next important setting is Discovery, where you configure port scanning behavior. You can choose to scan only common ports, all ports, or create a custom port specification.
For our demonstration, we will select “Port scan (all ports).”
 
The next setting you need to set is under Assessment, where you will select the type of scan you want.
 “default,” “scan for known web vulnerabilities,” “scan for all web vulnerabilities (quick),” “scan for all web vulnerabilities (complex),” ή “custom.”
For our demonstration, we will select “Scan for known web vulnerabilities.”
 
You can explore additional settings such as reporting options and advanced configurations.
The Credentials tab allows you to enter credentials such as SSH keys or Windows accounts to perform credentialed scans.
The settings we’ve covered will get you started with a basic vulnerability scan. You can customize them further as you become familiar with its capabilities.
Save all configured scan settings before starting the vulnerability scan by clicking “Save.”
 
Once you have saved your settings, you can start scanning by going to “My Scans” and clicking the play button.
 
The scan will take some time to complete. Once it’s done, you’ll see a tick next to the “Last Scanned.” column.
Click on your scan to go to the scan details page.
 
Now, we can look at the vulnerabilities found in the scan results.
 
 
Here is a breakdown of the various sections of the results page.
•	hosts: Shows the number of hosts scanned, which is one in our case.
•	Vulnerabilities: The total number of vulnerabilities found.
•	Remediations: Suggests the number of recommended remedial actions.
•	Notes: A note that provides additional information about the scan.
•	History: Indicates that there is a historical record of this scan.
•	Host IP Address (192.168.37.144): The specific IP address of the scanned host.
•	Vulnerability Severity Bars: Represents the number of vulnerabilities by severity — Critical (39), High (35), Medium (52), Low (7), and Info (211).
•	Scan Details Section: Provides details on the scan policy used, scan status, base severity (CVSS v3.0), scanner type (Local Scanner), start and end time, and total scan duration (25 minutes).
•	Vulnerabilities Pie Chart: Representation of vulnerabilities categorized by severity — Critical, High, Medium, Low, and Info.
To see the vulnerabilities in detail, click on the “Vulnerabilities” tab. This lists all detected vulnerabilities, which can be filtered by severity, CVSS score, VPR rating, name, family or number.
We have filtered them based on CVSS.
 
Let’s take a quick look at the “NFS Exported Share Name Disclosure” vulnerability to see what information Nessus provides.
 
The vulnerability details provided by Nessus include a description of the problem, suggested solutions to remediate it, evidence of the vulnerability found, and the specific port where it was detected.

Nessus report
Finally, we’ll show you how to create and export a Nessus report in a format that can be easily shared with stakeholders or other team members.
This report will provide an overview of the vulnerabilities found during the scan and recommendations for remediation.
Click the “Report” button from the scan results to configure your report. You can choose whether you want the report in HTML, PDF or CSV.
You can also choose the reference template. Once done, click “Generate Report.”
 
The report will be generated and downloaded to your system.
 

Conclusion
By following this guide, you will know how to install Nessus on both Kali and Windows.
We’ve also shown you some of its capabilities, including running a basic scan and generating a report that you can share with your team or clients.
Nessus is a powerful scanner and we encourage you to test its capabilities on your network to identify any potential vulnerabilities.
