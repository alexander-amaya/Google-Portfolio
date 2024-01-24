# Apply OS Hardening Techniques

## Scenario <br></br>
You are a cybersecurity analyst for yummyrecipesforme.com, a website that sells recipes and cookbooks. A disgruntled baker has decided to publish the website’s best-selling recipes for the public to access for free. 

The baker executed a brute force attack to gain access to the web host. They repeatedly entered several known default passwords for the administrative account until they correctly guessed the right one. After they obtained the login credentials, they were able to access the admin panel and change the website’s source code. They embedded a javascript function in the source code that prompted visitors to download and run a file upon visiting the website. After running the downloaded file, the customers are redirected to a fake version of the website where the seller’s recipes are now available for free.

Several hours after the attack, multiple customers emailed yummyrecipesforme’s helpdesk. They complained that the company’s website had prompted them to download a file to update their browsers. The customers claimed that, after running the file, the address of the website changed and their personal computers began running more slowly. 

In response to this incident, the website owner tries to log in to the admin panel but is unable to, so they reach out to the website hosting provider. You and other cybersecurity analysts are tasked with investigating this security event.

To address the incident, you create a sandbox environment to observe the suspicious website behavior. You run the network protocol analyzer tcpdump, then type in the URL for the website, yummyrecipesforme.com. As soon as the website loads, you are prompted to download an executable file to update your browser. You accept the download and allow the file to run. You then observe that your browser redirects you to a different URL, greatrecipesforme.com, which is designed to look like the original site. However, the recipes your company sells are now posted for free on the new website.  

The logs show the following process:

The browser requests a DNS resolution of the yummyrecipesforme.com URL.

The DNS replies with the correct IP address. 

The browser initiates an HTTP request for the webpage.

The browser initiates the download of the malware.

The browser requests another DNS resolution for greatrecipesforme.com.

The DNS server responds with the new IP address.

The browser initiates an HTTP request to the new IP address.

A senior analyst confirms that the website was compromised. The analyst checks the source code for the website. They notice that javascript code had been added to prompt website visitors to download an executable file. Analysis of the downloaded file found a script that redirects the visitors’ browsers from yummyrecipesforme.com to greatrecipesforme.com. 

The cybersecurity team reports that the web server was impacted by a brute force attack. The disgruntled baker was able to guess the password easily because the admin password was still set to the default password. Additionally, there were no controls in place to prevent a brute force attack. 

Your job is to document the incident in detail, including identifying the network protocols used to establish the connection between the user and the website.  You should also recommend a security action to take to prevent brute force attacks in the future.


## Response
<br></br>

### Part 1: Identify the netowrk protocol involved in the incident

The network protocol involved is HTTP. Running tcpdump and accessing the yummyrecipiesforme.com website we were able to use the log files provided as evidence to come to this conclusion. The malicious file is observed being transported to the users computers using the HTTO oriticik at the application layer.

### Part 2: Document the incident

Several customers contacted the website stating that when they visited they were prompted to download and run a file that asked them to update their browsers. Their personal computers have been operating slowley ever seince. The website owner tried logging into the website sever but noticed they were locked out of their account. 

The analyst used a sandbox environment to test the website without directly impacting the company network. The analyst ran tcpdump to capture the network and protocol traffic packets and that verfied what the cusomers were saying. The browser redirected the analyst to a fake website (greatrecipesforme.com) that looked identical to the original website (yummyrecipiesforme.com).

The cybersecurity analyst inspected the tcpdump log and observed that the browser initially requested the IP address for the yummyrecipesforme.com website. Once the connection with the website was established over the HTTP protocol, the analyst recalled downloading and executing the file. The logs showed a sudden change in network traffic as the browser requested a new IP resolution for the greatrecipesforme.com URL. The network traffic was then rerouted to the new IP address for the greatrecipesforme.com website.

The senior analyst analyzed the source code for the websites and downloaded file. The analyst discovered that an attack had manipulated the website to add code that prompted the users to download a malicious file disguised as a browser update. Since the website owner stated that they had been locked out of their administrator account, the team believes the attacker used a brute force attack to access the account and change the admin password. The execution of the malicious file compromised the end users’ computers.

### Part 3: Reccomend one remediation for brute force attacks


The best way that this could have been avoided is by changing the default administrator password. Along with changing it from the start, changing the password every 6 months to a year will also help establish a stronger defense against malicious actors.
