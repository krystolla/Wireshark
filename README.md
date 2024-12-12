# XYZ Hospital Network Traffic Analysis

## Description
This project focuses on analyzing network traffic to investigate a DDoS attack on XYZ Hospital's records server. The goal is to identify vulnerabilities, understand the impact, and propose effective mitigation strategies to enhance the hospital's IT security.

## Project Overview
This project involved analyzing network traffic using Wireshark to identify the cause of a server issue at XYZ Hospital providing mitigation strategies. ICMP packet behaviors are examined to investigate potential attacks with findings and solutions to prevent future incidents.

## Problem Statement
XYZ Hospital's records server became unresponsive, displaying error messages when accessed by staff. Preliminary investigations indicated that records server has a problem as the login attempt into the server using the <b> IP address 200.200.1.77</b> , was unsuccessful. The further investigation aims to confirm the nature of the issue, identify vulnerabilities, and propose mitigation strategies to prevent future incidents.

## Tools Used
Wireshark for packet analysis

## File Included
[ICMP Sample.pcapng](https://github.com/krystolla/WiresharkAnalysis/blob/648f3a2e5a03305644ab8a02a100a5cdc78bf9f5/ICMP%20Sample.pcapng)

## Investigation Plan
-	Explain the network traffic associated with the connection to the records server and ICMP protocol.
-	Examine the record server’s ICMP Protocol behaviour through a capture file and compare it to normal behaviour.
-	Explain the compromised security goals and trace back to the system’s vulnerabilities and acting threats to determine whether this access denial is an attack.
-	Discuss the technical, organisational and social stability implications of this incident.
-	Recommend potential mitigation strategies with detailed explanations.

## Investigation Walk-through
### 1.	Normal ICMP Protocol Behaviour Description
Network traffic refers to the flow of data in a communication network, where the speed of the flow is determined by the amount of data, or data packets, travelling. The Internet Control Message Protocol (ICMP) is deployed by network hardware such as routers to ensure packets arrive at their intended destination. As part of the Open System Interconnection (OSI) Reference Model’s network layer, the ICMP is also used to detect anomalies in the traffic flow. However, ICMP is only capable of detecting errors, not correcting them.
<br />
<br />
One way ICMP troubleshoot network errors is the ping utility. Ping refers to a command-line tool that diagnoses network communication via the echo queries embedded in ICMP. These queries consist of requests which ICMP encapsulate as messages inside Internet Protocol (IP) diagrams to send to a computer. When done successfully, the computer will receive an echo reply for the ICMP (Figure 1).
<br/>
<img src="https://i.imgur.com/BNGeEZW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

### 2.	ICMP Misuse and Glimpse of the Capture File
Despite ICMP’s functionality, the protocol can be exploited by attackers to overwhelm computers. One common attack scheme is Distributed Denial of Services (DDoS), where the attackers send multiple ICMP echo request messages (pings) to a computer simultaneously. Responding to each message requires resources, and when dealing with a wave of such requests, the computer will become overwhelmed and shut down. Furthermore, the simultaneous processing of such requests will not generate any responses. This pattern has also been observed in the capture file of the data packets since the Hospital XYZ database server incident (Figure 2). From this capture file, the possibility of a DDoS attack occurrence is likely.
<br/>
<img src="https://i.imgur.com/u1W4R6n.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

### 3.	Contrast with normal behaviours
Normal ICMP behaviour includes one response from the host’s IP following the IP requesting the ping. As it is described in Figure 1, there are normally 4 sequences of ping request-receive. In contrast, we have observed the following 3 abnormal behaviours from the packet capture of XYZ Hospital’s records server:
#### 3.1	Multiple ping requests from various IP addresses to the server IP
Figure 3-1
<br/>
<img src="https://i.imgur.com/FmI1puo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
#### 3.2	No response from the server IP
Figure 3-2
<br/>
<img src="https://i.imgur.com/uMEZOiJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
#### 3.3	All the ping requests happened in quick succession
Figure 3-3
<br/>
<img src="https://i.imgur.com/5fmt7r1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

### 4.	Security goals, system vulnerabilities and acting threats
#### 4.1 Security Goals
XYZ Hospital staff were unable to access the records, and each attempt prompted an error message. Thus, the security goal compromised was Availability.
#### 4.2 Vulnerabilities
There are several possible vulnerabilities regarding the ICMP discovered from the preliminary investigation such as network traffic congestion, IP address leaks, firewall misconfiguration, and lack of management policy associated with security upgrade policy or contingency plan for staff.
#### 4.3 Threat
The most plausible threat that can act on these vulnerabilities is an individual or group confirming these vulnerabilities. With the network traffic loosely monitored and no security installed, individuals with malicious intents can act upon these confirmed vulnerabilities and conduct a DDoS attack. This possibility is also supported by the capture file in Figure 2, where the ICMP deviates from its normal behaviour. Thus, these vulnerabilities and evidence confirm that the unresponsive server is the aftermath of a DDoS attack. However, the real source of the attack is largely unknown owing to the sources of this attack occurring randomly.

### 5.	Technical, organisational, and social implications
The service disruption caused by the DDoS attack not only increases the likelihood of additional security issues such as further hacking attempts but also incurs costs related to the allocation of technical resources for system recovery. Furthermore, this complex issue undermines the hospital's operational efficiency and reduces staff productivity. Additionally, it negatively impacts the hospital's reputation.

### 6.	Potential mitigation strategies
To prevent DDoS attack from transpiring, deploying access control and a gateway firewall are suggested. Continuous incident detection and response can detect abnormal activities before the spread of DDoS attacks. To recover from the damage of a DDoS, regular backups are needed. It is also important to test restoration when completing the first backup and performing backups annually and when there is a change in the IT infrastructure and personnel.

## Conclusion
The investigation confirmed that the server outage at XYZ Hospital resulted from a DDoS attack, compromising the security goal of availability. Analysis of ICMP behavior and packet captures revealed network vulnerabilities that were exploited during the incident. Some mitigation strategies has been recommended to prevent future attacks and secure the hospital's IT infrastructure effectively.
