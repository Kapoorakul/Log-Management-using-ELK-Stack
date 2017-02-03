# Log-Management-using-ELK-Stack
Log management

In this series, I will exploring log mangement in the Network Infrastructure from varios devices and services running on those devices. 
For example, I have deployed pfSensse, and configured it to generate the firewall logs. pfSense is an open source project, and comes with with array of services that we can deploy along with it. The additional services or the package i deployed along with it were Snort. Snort is also an open source IDS/IPS service. Using snort, I can filter inbound as well as outbound traffic on variety of use cases. There are ample number of rule sets that you can download. These rules can then be used against the traffic. If it matches then you can generate alert, and optionally drop the traffic.
pfSense comes with GUI mode as well in addition to command line. It has in built fucntionality of forwarding the logs (for example firewall, system etc) to the Syslog server over UDP/TCP port 514.
I have syslog server running on the management network listening on port UDP/TCP port 514. 
Now, comes the fun stuff. 
We know that network logs can be very overwhelming at times, therefore i used a great open source tool called ELK stack. 
It is an abbreviation for ELastic + Logstash + Kibana. How can ELK stack help me with log management, you may ask. Well, since we know that network logs have predefined format, for instance:
"MM Day YYYY MM:HH:SS hostname log-message"
From the above log line we can extract each and everything, like day,date,year,month,host,IP,process-id,protocol and many more things.Logstash can help us. It uses regex which can be matched against the each log line and extract and tag the interesting Feild values with a Feild name. 
