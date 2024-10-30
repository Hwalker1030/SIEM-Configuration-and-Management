# SIEM-Configuration-and-Management
Vizualizing and setting up alerts through Elastic Stack SIEM
<h1>Project Overview</h1>
In this project, I will be demonstrating how to set up and configure Elastic Stack SIEM in a Home Lab Environment utilizing VMWARE and Kali Linux; Aquired hands-on experience generating and analyzing security events using Nmap on Kali Linux; Creating and vizualizing real-time alerts. 



<br> This project follows along Abdullahi Ali's blog post: https://medium.com/@aali23/a-simple-elastic-siem-lab-6765159ee2b2 



<h1>Setup</h1>
For this project, I utilized VMware to set up a Virtual Machine running Linux OS to create an Endpoint for my agent. After my agent was successfully installed on the endpoint, I began to run linux command "nmap -p- localhost" to generate security events.

![Screenshot 2024-10-30 045909](https://github.com/user-attachments/assets/60701928-5a42-4835-b915-147f7ae78ee4)


Now that I created security events using the Nmap command in the Kali VM, I can now analyze the logs in the Elastic SIEM. 
![Logs](https://github.com/user-attachments/assets/8770b32d-af03-482e-8a85-ab99771eae2c)

I utilized the Elastic SIEM search query filter to get a better understanding on how to detect and investigate security incidents.

Here I used "process.args: nmap" in the search query.


![argsnmp](https://github.com/user-attachments/assets/fcb86649-7001-4d45-8898-f5ae63db7919)


![nmpargsinlog](https://github.com/user-attachments/assets/ebaca932-065f-4b32-8ad4-c587eb4ffe92)


Now that I had a better idea on how to query to identify and investigate security incidents, I wanted to utilize the visualization feature in the Elastic SIEM Application. I went ahead and opened the analytics dashboard but did not use any provided templates that Elastic provides to get a better understanding on how to visualize these events. Visualizing with graphs helps identify patterns or anomalies in the data provided.

![Create Dashboard](https://github.com/user-attachments/assets/329178e3-7e6e-463f-936e-3c752db2d7b9)

I was toying around with the features provided by the Elastic SIEM Application and was able to change the vizualization of data. Here I event counts timestamped within 15 minute period in this chart.

![Count of records vizualiation](https://github.com/user-attachments/assets/a624ab38-66bc-401e-8b9b-cbc3e2862a93)



I was also able to utilize the alert feature, which is a crucial tool for detecting security incident and being able to respond to them in a timely manner. With this, I set up the SIEM to send an alert to my email if "Nmap" was detected in the event logs. 


![Alert Security](https://github.com/user-attachments/assets/0039279d-1c6c-406f-af4c-e88172c71beb)


![rulenmap](https://github.com/user-attachments/assets/655e9cbe-e05f-4d44-a191-a228c2b14ba3)

I wanted to test the monitoring process of the SIEM, so I went and ran the "Nmap" command on my endpoint.

![ran nmap](https://github.com/user-attachments/assets/d5e9b6bf-2727-459f-84a4-eb2d195d8eb2)


And received my notification through email successfully!

![nmapemail](https://github.com/user-attachments/assets/d30c577a-81de-4c46-b766-dc17daa3f17d)




