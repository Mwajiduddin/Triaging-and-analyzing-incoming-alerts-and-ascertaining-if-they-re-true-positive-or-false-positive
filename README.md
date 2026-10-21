<h1 align="center">SOC Simulator: Phishing Unfolding - TryHackMe</h1>

In this SOC Simulator lab from TryHackMe, we’ll be triaging and analyzing 35 alerts coming in real-time to differentiate if any of these alerts are true positive. If an alert is a true positive, we’ll have to document our findings and explain why it’s a true positive by writing up a report.
At our disposal to assist us, we are given access to a VM to access the attachments from the alerts, TryDetectThis which is TryHackMe’s file and URL analyzer, and Elastic to look at the logs in greater detail.

<p align="center">
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/0.png" />
</p>

<h2 align="center">Alert ID 1000:</h2>
This is the first alert in the queue which looks to be a phishing alert from the sender, eileen@trendymillineryco.me. It’s odd that an email is asking for banking details but the sender’s domain isn’t malicious based from TryDetectThis and there are no malicious attachments nor suspicious hyperlinks in this email so this alert is false positive.

<p align="center">
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/1.png" />
</p>

Answer: False positive
<p align="center">
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/2.png" />
</p>


<h2 align="center">Alert ID 1001:</h2>
After finishing the first alert, more alerts started coming into the queue.

<p align="center">
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/3.png" />
</p>

<p align="center">
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/1001.png" />
</p>
Answer: False positive
<p align="center">
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/4.png" />
</p>

<h2 align="center">Alert ID 1002:</h2>
<p align="center">
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/1002.png" />
</p>
Answer: False positive
<p align="center">
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/5.png" />
</p>

<h2 align="center">Alert ID 1003:</h2> 
<p align="center">
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/1003.png" />
</p>
Answer: False positive, same as the alert 1000, there’s no malicious attachments nor suspicious hyperlinks in this email so this alert is false positive. Also the email domain appears to be legitimate according to TryDetectThis.
<p align="center">
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/8.png" />
</p>
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/6.png" />
</p>


<h2 align="center">Alert ID 1004:</h2> 
<p align="center">
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/1004.png" />
</p>
Answer: False positive, same as the alert 1000, there’s no malicious attachments nor suspicious hyperlinks in this email so this alert is false positive. Also the email domain appears to be legitimate according to TryDetectThis.
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/9.png" />
</p>
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/6.png" />
</p>


<h2 align="center">Alert ID 1005:</h2> 
<p align="center">
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/1005.png" />
</p>
A suspected phishing email was sent to the CEO with a zip attachment that has a typo in it, this should start to raise some flags.
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/10.png" />
</p>

If we were to search up Michael’s email address as the recipient in Elastic, we found a log that shows the same named zip file:
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/19.png" />
</p>

From the TryDetectThis, scanning the zip attachment yields nothing malicious but inside the zip there’s a file with a typo and scanning it does yield that it’s malicious.
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/11.png" />
</p>
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/12.png" />
</p>

Answer: True positive
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/13.png" />
</p>






<h2 align="center">Alert IDs 1006-1010:</h2> 
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/14.png" />
</p>
<p align="center">
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/1006.png" />
</p>
<p align="center">
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/1007.png" />
</p>
<p align="center">
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/1008.png" />
</p>
<p align="center">
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/1009.png" />
</p>
<p align="center">
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/1010.png" />
</p>
These next 5 alerts are stated as suspicious processes, all of them are legitimate Windows processes so these are false positives. The processes in question: 


Svchost.exe: host Windows services such as networking or system management services

Rdpclip.exe: connects the clipboard functionality across Remote Desktop sessions

Taskhostw.exe: executes Windows tasks and DLL-based components

WUDFHost.exe: host drivers through Windows User-Mode Driver Framework (UMDF), this allows drivers to operate outside the Windows kernel

Answer: False positive
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/15.png" />
</p>

<h2 align="center">Alert ID 1020:</h2>
After finishing up alerts 1006-1010, we started to receive alerts that were in medium and high severity in the queue so instead of continuing chronologically at alert 1011 let's take a look at the high severity once first:
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/16.png" />
</p>

All of the high level severity alerts deal with prompting Powershell to use the Windows DNS lookup tool, nslookup.exe, from a folder called exfiltration, to query weird looking domain names. 
And all of these high level severity alerts are happening on one device (win-3450) that belongs to the CEO, Michael Ascot. 
Let's take a look at the alerts that came right before the high severity alerts to get a better understanding of what’s happening starting at alert ID 1020, named "Powershell Script in Downloads Folder":
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/17.png" />
</p>
Doing some research, the name of the script is called PowerView.ps1 and it is a Powershell script that is designed as a network reconnaissance tool to help map out the Windows network, identify priority accounts and uncover potential vulnerabilities.
Why is there a powershell script running in the Downloads folder on the CEO’s device? This looks bad. 
The name of Michael Ascot’s device is win-3450, searching this up in Elastic brings up a lot of results and one of the logs shows concerning evidence of controlling Michael’s computer remotely:
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/18.png" />
</p>
Answer: We can conclude that this alert is a true positive and needs to be escalated so that this can be handled immediately. 
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/20.png" />
</p>


<h2 align="center">Alert ID 1022-1024:</h2>

Skipping alert 1021 since from a glance it doesn’t look like a true positive and has a low severity.
Alert 1022 seems more concerning as a network drive was mapped to the local drive using Powershell. 
So essentially net.exe was launched by Powershell to access the folder name SSF-FinancialRecords that’s located on the FILESRV-01 server and the malicious actor plans on retrieving this folder from the mapped Z: drive. 
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/21.png" />
</p>

Alert 1023 shows that this command line was ran by Powershell:
“C:\\Windows\system32\Robocopy.exe” . C:\\Users\michael.ascot\downloads\exfiltration /E
This essentially means that the Windows file-copying tool called Robocopy.exe was launched by Powershell to copy files from the mapped network Z drive into a folder called exfiltration.
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/22.png" />
</p>

And Alert 1024 describes the network Z drive being disconnected, essentially the malicious actor is trying to cover his tracks. Basically data exfiltration is happening in Alert 1022, 1023, and 1024, so true positive.
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/23.png" />
</p>
 
Answer: True positive
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/24.png" />
</p>


<h2 align="center">Alert ID 1025-1034:</h2>
<p align="center">
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/1025.png" />
</p>
<p align="center">
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/1026.png" />
</p>
<p align="center">
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/1027.png" />
</p>
<p align="center">
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/1034.png" />
</p>
These alerts are all true positive because all of them are utilizing Powershell to use the Windows DNS lookup tool, nslookup.exe to lookup odd and suspicious domain names where there’s a string of characters at the beginning. 
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/25.1.png" />
</p>
For the inexperienced, the first portion look to be gibberish but those are actually Base64-encoded text. 
Base64 is basically disguising a file (image, video, binary data, etc.) into random text characters. Base64 exists because back in the old days you couldn't simply send media as attachments, you could only send text. So you have to convert the media file to text then send and the recipient had to that text back to the original media file. That's how the bad actor is exfiltrating the files, he's encoding them to Base64.

What’s probably happening is DNS tunneling. The malicious actor is querying these weird domain names as a way to exfiltrate the data from the “exfiltration” folder back to him and since DNS protocol is so commonly used, DNS traffic is trusted and the attacker used this as a way to exfiltrate the data. 
Answer: True positive
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/25.png" />
</p>


After submitting the alerts as true positives, I was notified that I’ve identified all the true positives so the remaining alerts that I hadn’t touched (1011-1019, 1021, and 1035) were false positives.
<img src="https://github.com/Mwajiduddin/Triaging-and-analyzing-incoming-alerts-and-ascertaining-if-they-re-true-positive-or-false-positive/blob/main/26.png" />
</p>


