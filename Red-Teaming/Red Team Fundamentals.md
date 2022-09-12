# Task 1: Introduction
Cybersecurity is a constant race between white hat hackers and black hat hackers. As threats in the cyber-world evolve, so does the need for more specialized services that allow companies to prepare for real attacks the best they can.

While conventional security engagements like vulnerability assessments and penetration tests could provide an excellent overview of the technical security posture of a company, they might overlook some other aspects that a real attacker can exploit. In that sense, we could say that conventional penetration tests are good at showing vulnerabilities so that you can take proactive measures but might not teach you how to respond to an actual ongoing attack by a motivated adversary.

### Room objectives
Learn about the basics of red team engagements
Identify the main components and stakeholders involved in a red team engagement
Understand the main differences between red teaming and other types of cybersecurity engagements

### Room prerequisites
Before beginning this room, familiarity with general hacking techniques is required. Although not strictly necessary, completing the Jr. Penetration Tester Learning Path is recommended.

---

# Task 2: Vulnerability Assessment and Penetration Tests Limitations
### Vulnerability Assessments

This is the simplest form of security assessment, and its main objective is to identify as many vulnerabilities in as many systems in the network as possible. To this end, concessions may be made to meet this goal effectively. For example, the attacker's machine may be allowlisted on the available security solutions to avoid interfering with the vulnerability discovery process. This makes sense since the objective is to look at every host on the network and evaluate its security posture individually while providing the most information to the company about where to focus its remediation efforts.

To summarize, a vulnerability assessment focuses on scanning hosts for vulnerabilities as individual entities so that security deficiencies can be identified and effective security measures can be deployed to protect the network in a prioritized manner. Most of the work can be done with automated tools and performed by operators without requiring much technical knowledge.

As an example, if you were to run a vulnerability assessment over a network, you would normally try to scan as many of the hosts as possible, but wouldn't actually try exploiting any vulnerabilities at all:

![image](https://user-images.githubusercontent.com/79099734/189602131-45675504-1248-4a1b-b0a0-d2082427e509.png)

### Penetration Tests
On top of scanning every single host for vulnerabilities, we often need to understand how they impact our network as a whole. Penetration tests add to vulnerability assessments by allowing the pentester to explore the impact of an attacker on the overall network by doing additional steps that include:

Attempt to exploit the vulnerabilities found on each system. This is important as sometimes a vulnerability might exist in a system, but compensatory controls in place effectively prevent its exploitation. It also allows us to test if we can use the detected vulnerabilities to compromise a given host.
Conduct post-exploitation tasks on any compromised host, allowing us to find if we can extract any helpful information from them or if we might use them to pivot to other hosts that were not previously accessible from where we stand.
Penetration tests might start by scanning for vulnerabilities just as a regular vulnerability assessment but provide further information on how an attacker can chain vulnerabilities to achieve specific goals. While its focus remains on identifying vulnerabilities and establishing measures to protect the network, it also considers the network as a whole ecosystem and how an attacker could profit from interactions between its components.

If we were to perform a penetration test using the same example network as before, on top of scanning all of the hosts on the network for vulnerabilities we would try confirm if they can be exploited in order to show the impact an attacker could have on the network: 

![image](https://user-images.githubusercontent.com/79099734/189602080-469a7f4c-dd11-4801-8257-788744571061.png)

By analyzing how an attacker could move around our network, we also gain a basic insight on possible security measure bypasses and our ability to detect a real threat actor to a certain extent, limited because the scope of a penetration test is usually extensive and Penetration testers don't care much about being loud or generating lots of alerts on security devices since time constraints on such projects often requires us to check the network in a short time.


### Advanced Persistent Threats and why Regular Pentesting is not Enough
While the conventional security engagements we have mentioned cover the finding of most technical vulnerabilities, there are limitations on such processes and the extent to which they can effectively prepare a company against a real attacker. Such limitations include:

![image](https://user-images.githubusercontent.com/79099734/189601976-06df36a5-d919-4860-b2b9-d09ac16bbb1a.png)

As a consequence, some aspects of penetration tests might significantly differ from a real attack, like:

Penetration tests are LOUD: Usually, pentesters won't put much effort into trying to go undetected. Unlike real attackers, they don't mind being easy to detect, as they have been contracted to find as many vulnerabilities as they can in as many hosts as possible.
Non-technical attack vectors might be overlooked: Attacks based on social engineering or physical intrusions are usually not included in what is tested.
Relaxation of security mechanisms: While doing a regular penetration test, some security mechanisms might be temporarily disabled or relaxed for the pentesting team in favor of efficiency. Although this might sound counterintuitive, it is essential to remember that pentesters have limited time to check the network. Therefore, it is usually desired not to waste their time searching for exotic ways to bypass IDS/IPS, WAF, intrusion deception or other security measures, but rather focus on reviewing critical technological infrastructure for vulnerabilities.
On the other hand, real attackers won't follow an ethical code and are mostly unrestricted in their actions. Nowadays, the most prominent threat actors are known as Advanced Persistent Threats (APT), which are highly skilled groups of attackers, usually sponsored by nations or organised criminal groups. They primarily target critical infrastructure, financial organisations, and government institutions. They are called persistent because the operations of these groups can remain undetected on compromised networks for long periods.


If a company is affected by an APT, would it be prepared to respond effectively? Could they detect the methods used to gain and maintain access on their networks if the attacker has been there for several months? What if the initial access was obtained because John at accounting opened a suspicious email attachment? What if a zero-day exploit was involved? Do previous penetration tests prepare us for this?


To provide a more realistic approach to security, red team Engagements were born.

---

# Task 3:  Red Team Engagements
