#### Documentation under process!!

`DDoS Attack Detection and Mitigation using Machine Learning`

![image](https://user-images.githubusercontent.com/78417411/204220907-67fb2338-1023-4404-8320-b7c2967bd0a3.png)
</div>
<h2>Table of Contents🧾</h2>

- [Introduction📌](#introduction)
- [Motivation](#motivation)
- [Objectives](#objectives)
- [Installation](#installation)
- [Literature Survey](#literature-Survey)
- [Implemented System](#implemented-system)
- [Description of the Implemented system](#description-of-the-implemented-system)
- [Software requirements specification](#software-requirements-specification)
- [System Design](#system-design)
- [Implementation](#implementation)
- [Testing](#testing)
- [Results & Discussion](#results-&-discussion)
- [Conclusion](#conclusion)
- [References](#references)
- [Appendix](#appendix)
<br>
<!-- --------------------------------------------------------------------------------------------------------------------------------------------------------- -->
### Project Team:
Om Srivastava (32201222114)  
Niladri Das (32201222119)  
Chirag Agarwal (32201222127)  
Arijeet Mukherjee (32201222092)  
Sujoy Karmakar (32201222118)

---

### Table of Contents

- [Introduction](#introduction)
- [Motivation](#motivation)
- [Objectives](#objectives)
- [Installation](#installation)
- [Literature Survey](#literature-survey)
- [Implemented System](#implemented-system)
- [System Design](#system-design)
- [Implementation](#implementation)
- [Testing](#testing)
- [Results and Discussion](#results-and-discussion)
- [Conclusion](#conclusion)
- [References](#references)
- [Appendix](#appendix)

---

### Introduction
A distributed denial-of-service (DDoS) attack disrupts the normal traffic of a targeted server, service, or network by overwhelming it with a flood of internet traffic. Multiple compromised systems are used as attack sources, including IoT devices. Effective mitigation is challenging, as distinguishing malicious traffic from legitimate users is complex.

### Motivation
Businesses relying on mission-critical applications cannot afford downtime. Software-Defined Networking (SDN) provides flexibility but is vulnerable to DDoS attacks, posing severe risks to data centers. Mitigating these threats is essential for maintaining service availability and security.

### Objectives
- Develop a network using Mininet and Ryu controller.
- Generate a dataset simulating network traffic.
- Apply the Random Forest algorithm to detect DDoS attacks.
- Implement a mitigation module to manage detected threats.

### Installation Instructions
1. Install VirtualBox or VMware Workstation.
2. Install Mininet-VM from the [Mininet releases](https://github.com/mininet/mininet/releases).
3. Install Ubuntu in VirtualBox.
4. Set up the Ryu controller from the [official documentation](https://ryu.readthedocs.io/en/latest/getting_started.html).
5. Clone the project repository:
   ```bash
   https://github.com/NilUwU/Minorp.git
   ```

#### Running the Controller
1. Check the IP address using:
   ```bash
   ifconfig
   ```
2. Navigate to the controller folder and start the Ryu controller:
   ```bash
   cd controller
   ryu-manager controller.py
   ```

#### Running Mininet
1. Switch to the Mininet directory:
   ```bash
   cd mininet
   ```
2. Update the controller IP address in `topology.py`.
3. Run the topology:
   ```bash
   sudo python topology.py
   ```

#### hping Commands for Traffic Simulation
```bash
# ICMP flood
hping3 -1 -V -d 120 -w 64 -p 80 --rand-source --flood

# SYN flood
hping3 -S -V -d 120 -w 64 -p 80 --rand-source --flood

# UDP flood
hping3 -2 -V -d 120 -w 64 -p 80 --rand-source --flood
```
---

### Literature Survey
Summaries of referenced works explore machine learning-based DDoS detection and mitigation models, emphasizing Random Forest, SVM, LSTM, and other approaches.

### System Design
The SDN architecture includes:
- **Application Layer**: Manages network applications like traffic engineering and security.
- **Control Layer**: Centralized SDN controller that governs policies and traffic flows.
- **Infrastructure Layer**: Physical switches and routers that forward traffic based on control plane instructions.

---

### Implementation
**Flow Collection Module**: Gathers traffic data using OpenFlow and extracts key flow identifiers.

**Detection Module**: Classifies traffic as normal or abnormal using flow-based detection with a Random Forest algorithm.

**Mitigation Module**: Prevents attacks by blocking Ethernet addresses associated with malicious flows.

---

### Testing
The system was evaluated by classifying online traffic and blocking detected malicious sources. Random Forest was found to deliver superior accuracy compared to other models.

---

### Results and Discussion
Performance evaluation showed that the Random Forest classifier achieved high detection accuracy without disrupting normal traffic.

---

### Conclusion
The proposed system uses machine learning to enhance DDoS detection and mitigation in SDN environments. Random Forest provides accurate classification and effective attack prevention with minimal impact on legitimate traffic.

---

### References
[1] Dong Li et al. (2018). Using SVM to Detect DDoS Attacks in SDN Network. IOP Conf. Ser.: Mater. Sci. Eng. 466 012003.  
[2] Yijie Li et al. (2019). DDoS Attack Detection Using Deep Belief Networks. IOP Conference Series.  
(Additional references as listed in the original document)

---

### Appendix
- **Glossary**: Defines key terms such as DDoS, SDN, and MAC address.
- **Tools**: Mininet, Ryu controller, VirtualBox, Python, Wireshark.


- Wireshark:Network Monitoring tool

