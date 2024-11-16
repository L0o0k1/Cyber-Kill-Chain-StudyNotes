### **Something to consider.**

1. **There is no _one-way to do_ a specific thing; there is always another way. That’s what search is made for…**
2. **There is a reason for calling it _phishing_. You have to be _patient_ to get what you want.**
3. **evilginx2 have some issues and complex setup problems and the DOC won’t be very helpful! that’s for obvious reasons. you may edit some problems so its highly recommended to have some Go-lang knowledge**
4. **Seek a Peek for the difference between evilginx2 and evilgophish**

---

### Pre-Engagement.

- **1- Research Your Target.**
  - It really depends on your target, and if it's one person or an organization with a lot of employees,
  - Know How Your Target Communicates (e-mails?, phone?, Discord?, etc.)
  - Know how they speak on their website. Knowing how they talk on their website will allow you to simulate their actual way and implement that in your phishing campaign.
  - Try to know some employees names; that's really helpful. One or two first names and last names can be different, and then create your target list...
  - Buy a domain from whatever you like (AWS Route 53, etc.). It's pretty cheap and mandatory.
  - Check your target domain and see how you could change a little bit of it to still be legitimate. ⇒ This is the most important part
  - Use https://altcodeunicode.com/ website to change your domain name and be a little sneaky!
- **2- Introduction to GoPhish.**
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

     Monitor who opened the email, clicked the links, submitted data (if any), or reported the email. This helps organizations identify patterns and weak points.

  7. **Self-hosted and API Support**:

     As a self-hosted tool, organizations maintain control over the data, and the API allows automation and integration with other security tools.

  8. **Multi-user Support**:

     Different teams or individuals can use GoPhish simultaneously to manage separate campaigns.
  ### ⇒ References:
  1- https://getgophish.com/
  2- https://docs.getgophish.com/user-guide/installation
  3- https://github.com/gophish/gophish
  In real basic defenation, we're going to go deeper!
  ```bash
  # First To Avoid much time for loading the GOPhish
  # Hit to templates -> statics -> base.html -> remove the fonts.google elements
  # Do The Same thing aboe For The Login Page ...
  # -------------------------------------------------
  # Follow the installation and configuration steps that provided in documentation until runing GoPhish up on your brwoser
  # sign in with : username: admin, Password: gophish
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
  # -> Redirect to the Original page/ Site {The Real One Ha!}
  #===
  ## ==> We Gonna use @Evilnginx2 so we will use our custom landing page
  #===**
  # -------------------------------------------------
  # 3- Configure @Email Templates: -> {What Ur email look like when it arrive to your trget}Take a real care on this one...
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
  ***
- **3- Introduction to _Evilginx2_ tool.**
  An advanced phishing tool designed to perform **man-in-the-middle (MITM)** attacks to steal credentials and session cookies from users. **It acts as a reverse proxy**, intercepting communication between a legitimate website (such as Gmail, Facebook, or Office365) and the target user, enabling attackers to capture **two-factor authentication (2FA) tokens** and **session cookies**.
  This makes it especially dangerous because, even if a user logs in with the correct credentials and provides an OTP (One-Time Password) from their authenticator, Evilginx2 can capture the **session cookie** and allow an attacker to log in without needing the password or the OTP in the future.
  ***
  ### **Key Features of Evilginx2**
  1. **Man-in-the-Middle Reverse Proxy Attack**
     - Evilginx2 acts as an intermediary between the user and the target site, forwarding requests while capturing login details and session cookies.
     - It Will be set between our victim and legitimate login page we will displayed!
  2. **Bypassing 2FA**
     - Even with 2FA enabled, Evilginx2 can steal valid session cookies, allowing attackers to bypass authentication without needing the OTP.
  3. **Phishing Kits and Templates**
     - Supports **phishing templates** for popular websites (like Google, Microsoft, Facebook) that replicate the original sites closely, making it hard for users to detect phishing attempts.
  4. **Session Cookie Hijacking**
     - By capturing cookies, attackers can impersonate the victim and maintain access to accounts until the session expires or is invalidated.
  5. **Stealth and Flexibility**
     - Evilginx2 can be deployed on a remote VPS and masked with **TLS certificates** (e.g., via Let's Encrypt) to create a secure-looking phishing site with HTTPS.
  ***
  ### **How It Works?**
  1. The attacker sets up Evilginx2 on a VPS, configures DNS, and deploys a phishing template for a target website.
  2. A phishing link (disguised as a legitimate website) is sent to the victim.
  3. When the victim clicks the link, they are presented with a **login page identical to the real one**.
  4. Evilginx2 captures the **username, password**, and **2FA code** during the login process.
  5. It forwards the session cookie to the attacker, who can then use it to log into the victim’s account without needing credentials or OTPs.
  ***
- **4- Introduction to AWS and Why AWS?.**
  - You Can Choose whatever you like OFC
  - We can use Route53 from Amazona, AKA we can purchase domain from amazon.
  - It Enable us to create a DNS Records.
  - It Provide us with Amazon EC2 Instances:
    - What is EC2 Instances:?
      Amazon EC2 (Elastic Compute Cloud) instances are **virtual servers** provided by Amazon Web Services (AWS) that offer scalable computing power. These instances allow you to run applications in the cloud instead of relying on physical servers, providing the flexibility to quickly launch, manage, and scale resources on-demand.
      ### Key Features of EC2 Instances:
      1. **Scalability:** You can increase or decrease the number of instances based on demand.
      2. **Choice of Instance Types:** A wide variety of configurations to fit different workloads (e.g., compute-optimized, memory-optimized, or GPU-optimized).
      3. **Pricing Models:**
         - **On-Demand:** Pay for compute capacity by the hour/second with no long-term commitment.
         - **Reserved:** Save up to 75% by committing to use instances for 1 or 3 years.
         - **Spot:** Purchase unused instances at a discount, though they can be interrupted by AWS when demand spikes.
      4. **Security:** Control access using Security Groups, VPNs, and AWS Identity and Access Management (IAM) policies.
      5. **Operating Systems:** Choose from Linux, Windows, or other OS images.
      ### Common Use Cases:
      - **Web Hosting:** Hosting websites and applications.
      - **Data Analysis:** Running big data or AI/ML workloads.
      - **Development and Testing:** Quick setup of environments for software development.
      - **Disaster Recovery:** Backup infrastructure to be used in case of failure.
      - In our case its a server and this server is gonna hosting our **_Evilginx2_** as also its gonna hosting GoPhish
      - This Server is actually What Our Victims will connected too..
      ### Instance Types:
      1. **General Purpose (e.g., t2, t3):** Balanced for general workloads like web servers.
      2. **Compute Optimized (e.g., c5):** High-performance computing for CPU-heavy tasks.
      3. **Memory Optimized (e.g., r5):** Large memory workloads like in-memory databases.
      4. **Storage Optimized (e.g., i3):** High I/O operations for databases and storage.
      5. **Accelerated Computing (e.g., p3, g5):** GPU instances for AI and deep learning.
  - You Can Configure your S3 Bucket to receive emails to your domain
  - We have amazon SES
    - What is amazon SES?
      Amazon Simple Email Service (Amazon SES) is a **cloud-based email sending service** offered by AWS that allows businesses and developers to send **transactional, marketing, and notification emails** efficiently and securely. It’s designed to provide high deliverability, scalability, and reliability while giving users control over their email sending infrastructure.
      ### Key Features of Amazon SES:
      1. **High Deliverability**: Amazon SES leverages AWS’s global infrastructure and spam detection measures to ensure your emails reach their intended recipients.
      2. **Scalable**: Whether sending a few emails per day or millions per week, SES can handle dynamic workloads without requiring server management.
      3. **Secure**: Supports **DKIM (DomainKeys Identified Mail)**, **SPF (Sender Policy Framework)**, and **DMARC** to prevent spoofing and improve email security.
      4. **Custom Email Templates**: Build dynamic and reusable email templates.
      5. **Bounce and Complaint Tracking**: Automates handling of bounces, complaints, and delivery failures.
      6. **Inbound Emails**: Besides sending emails, SES can also receive emails and store them in Amazon S3 or trigger Lambda functions for processing.
      7. **Integration**: Easily integrates with **Amazon SNS (Simple Notification Service)**, **Lambda**, and **CloudWatch** for logging, notifications, and automated workflows.
      ### Common Use Cases:
      - **Transactional Emails**: Sending password resets, order confirmations, and account notifications.
      - **Marketing Campaigns**: Distributing newsletters and promotional emails.
      - **Automated Email Notifications**: Alerting users about system activities, invoices, or status updates.
      - **Email Integration in Applications**: Enabling apps to send emails via an API or SMTP interface.
        1. That will allow you to verify your spoof domain and allow you to send email from it
      ### Pricing:
      Amazon SES has a **pay-as-you-go** model, with charges based on:
      - Number of emails sent
      - Data transfer (outbound emails)
      - Attachments included
        If your emails are sent from an **Amazon EC2 instance**, the first 62,000 emails per month are free.
      ***
      Amazon SES is particularly useful for developers who need to integrate email functionality into applications without worrying about setting up or managing their own email servers.
- **5- Creating Target Email List.**
  - One of the most important steps and the easiest one also ..
  - Go to the Target Web page → About → seek any employers names, emails, accounts or LinkedIn, etc..
  - Identify how they using their email scheme ( first name + last name, first letter and last name, etc..)
  - Use [Phonebook.cz](http://Phonebook.cz) to check your target. It will give you some emails related to your target scheme, analyze the email scheme pattern and how they use it. → Put the phonebook results into txt file.
  - Go to their LinkedIn if they have → Jobs Page → seek the recruiters accounts, Move to People Page and see how work for them …
  - **_CrossLinked_**`{tool}` : Will do searching for you to automate the recon process in this phase ..
  - Pretty Lovely extension for this ⇒ https://chromewebstore.google.com/detail/findthatlead-email-finder/lkpekgkhmldknbcgjicjkomphkhhdkjj?hl=en-GB&pli=1
  ```bash
  # Clone the Repo an install req -->
  ~$ git clone https://repo
  ~$ cd ***CrossLinked***
  ~$ pip install -r req.txt
  # -------------------------------------
  #  Running it :
  ~$ Python3 crosslinked.py -f '{firstname}.{lastname}@OrgaName.net' OrgaName # Adding the email format..
  # -------------------------------------
  # Cat The names.txt will find what you came for ..
  ```
  - **6- 🚩 Corporate Recon(OSINT). ⇒ `Plus`**
    **⇒ Corporate reconnaissance consists of investigating critical things such as contracts, nancials, history, subsidiaries, organizational structure, governmental regulations, and third-party vendors.**
    ***
    ## 1- Searching for Personnel:
    1. [\*\*Google Dorks](https://www.exploit-db.com/google-hacking-database) : ⇒ We can find key people within an organization who may be targeted for an attack.\*\*
    ```bash
    **=> site:linkedin.com “system admin”+”company name.”
    # System Admin can be replaced with any job title that would be a rich
    # source for information leaks within a particular company.
    # You can narrow this search down by adding/replacing operators such as
     intext: resume “ firstname lastname.”**
    ```
    ***
    ## 2- Searching for Emails and Breach Data:
    1. [\*\*Hunter.io](http://hunter.io/) ⇒ For corporate email addresses.\*\*
    **⇒ It scrapes the web for the emails associated with that domain as well as the naming conventions that the company uses.**
    ⇒ **It allows us to select the job title which immediately keys us into the people we should then search on social media for information leaks.**
    **⇒ Has is the ability to select between personal and generic emails.**
    > **_When we switch to general emails we get a list of emails from potentially shared email accounts. If employees are sharing the account there is an increased chance of it being found in a breach and used in an attack_**
    —
    1. [\*\*Spiderfoot](https://github.com/smicallef/spiderfoot) : ⇒ Another option for discovering emails\*\*
    **⇒ Spiderfoot uses modules to run all sorts of domain recon but more specifically it uses a
    hunter.io module for emails.**
    **⇒ If you have a haveIbeenPwned API you can run that against all of the emails right in one spot.**
    —
    1. [\*\*HaveIbeenPwned](https://haveibeenpwned.com/) : ⇒ Once all of the company emails have been collected and compiled, we can run them through Haveibeenpwned to check if any emails have been found in a breach.\*\*
    **⇒ Haveibeenpwned has an API so you can run batches of emails through at once and it spits out breach information for each.**
    ***
    ## 3- Searching for Company Structure:
    1. **Company Websites ⇒ The first stop for determining the organizational structure is the company website.(About Us page)**
    **⇒ If they don’t have an obvious page for the company structure you can try using a Google Dork that searches for an org chart on their website such as:**
    ```
    **intitle: “org chart” site:website.com**
    ```
    **⇒ In This We Care About :**
    - [ ] **Finding the social media profiles of people with privileged access**
    - [ ] **Think C-suites and System Administrator**
    - [ ] **The company technology uses**
    - [ ] **Private business dealings**
    - [ ] **Day-to-Day activities may be exposed through business resumes**
    - [ ] **Personal social media pages**
    - [ ] **Personal LinkedIn profiles**
    ***
    ## 4- Searching for Financials & Filings:
    1. [\*\*Corporation Wiki](https://www.corporationwiki.com/): ⇒ Allows us to search for Trademarks, Bank Data, and Company information.\*\*
    2. [\*\*Enigma](https://www.enigma.com/) : ⇒ Public data sources from state and federal records as well as SEC filings and frozen assets.\*\*
    3. [\*\*Open Corporates](https://opencorporates.com/) : ⇒ Allows you to input a company and select the jurisdiction, data held, current status, and company type when searching.\*\*
    4. [\*\*US Security and Exchange Commission](https://www.sec.gov/) : ⇒ The SEC EDGAR Search is a database of Security and Exchange Commission filings up to the current year.\*\*
    ***
    ## 5- Finding a Specific Company & Their Connections:
    1. [\*\*Corporation Directory](https://corporation.directory/secstates) : ⇒ is a website where we can search for state corporation registries. Each registry is maintained by the specific states and therefore they all have different results. The trick for this site is not to use the search function which requires a subscription.\*\*
    2. [\*\*Little Sis](https://littlesis.org/) : ⇒ “a grassroots watchdog network connecting the dots between the world’s most powerful people and organizations.”\*\*
    **⇒ For example, when I searched for “Jeff Bozos” I got his business positions, relationships, charitable donations, and political contributions.**
    1. [\*\*Thomas](https://www.thomasnet.com/) : ⇒ is a search tool for finding Suppliers for specific products. We can search by product category, company, and brand. Searching for pharmaceutical suppliers gives us a whole lot of results that we can then narrow down by region.\*\*
- **7- Bypassing Spam Filters and Timing.**
  - Common Methods:
    ### 1. **Email Spoofing Techniques.**
    - **Spoofing "From" Headers**: Faking the sender’s email address to appear as a trusted entity.
    - **Display Name Spoofing**: Changing the display name to impersonate a legitimate contact, such as "John Doe [random@email.com](mailto:random@email.com)".
    - **Compromised Account Abuse**: Sending spam or phishing emails from legitimate but hacked accounts to bypass filters.
    ***
    ### 2. **Use of Trusted or Whitelisted Domains**
    - **Open Relay Servers**: Sending emails via poorly configured SMTP servers that allow unauthenticated relays.
    - **Using Email Providers with Good Reputation**: Abusing legitimate services (e.g., Gmail, Microsoft Outlook) to reduce suspicion.
    - **DKIM/DMARC/SPF Bypass: Using misconfigured or outdated DNS records to trick email filters into marking the email as legitimate. ⇒ Dig Deeper in this !**
    ***
    ### 3. **Obfuscation and Encoding Tricks**
    - **Hex/Unicode Encoding**: Hiding malicious content or keywords with character encoding to evade detection (e.g., "V\u0069agra").
    - **Image-based Spam**: Embedding text in images instead of plain text to prevent keyword detection.
    - **HTML Obfuscation**: Inserting random HTML tags (like `<span>` or `<font>`) in the middle of keywords (e.g., "V<span>a</span>gra").
    - **Base64 Encoding**: Hiding payloads (e.g., malicious links) in encoded formats like Base64.
    ***
    ### 4. **Evasion Through Content and Behavioral Techniques**
    - **Dynamic Content Generation**: Using rotating content or links in emails to change messages slightly with every send.
    - **Word Salting**: Adding irrelevant or innocuous words between spam content to confuse filters.
    - **Delaying Spam Waves**: Sending spam in small batches to avoid rate-based detection.
    - **Zero-Day Spam Campaigns**: Leveraging newly created domains or content before blacklists update.
    ***
    ### 5. **Attachment-based Evasion**
    - **Malicious File Types**: Sending spam with embedded malware (e.g., PDFs, Office documents) to exploit file parsing.
    - **Password-Protected Attachments**: Enclosing malicious files in password-protected archives to prevent automated scanning.
    - **Archive Nesting**: Embedding malicious files deep inside multiple compressed layers to evade filters.
    ***
    ### 6. **URL-based Techniques**
    - **Shortened URLs**: Using URL shorteners (e.g., [bit.ly](http://bit.ly/)) to hide malicious links.
    - **Redirect Chains**: Leading users through multiple redirects before landing on a phishing site.
    - **Look-alike Domains**: Registering domains that visually resemble legitimate sites (e.g., "[paypa1.com](http://paypa1.com/)").
    - **Homograph Attacks**: Using internationalized domain names (IDNs) that look similar to trusted domains (e.g., "[pаypal.com](http://xn--pypal-4ve.com/)").
    ***
    ### 7. **Exploiting Filter Blind Spots**
    - **Social Engineering Content**: Crafting emails that appear personal or urgent to trick users into interacting.
    - **Thread Hijacking**: Inserting spam into ongoing email conversations to exploit trust.
    - **Graymail Patterns**: Mimicking newsletters, promotional emails, or low-priority business emails to avoid suspicion.
    ***
    ### 8. **Time-based Evasion Tactics**
    - **Delayed Sending**: Timing spam during weekends or holidays when filter admins are less active.
    - **Self-destructing Links or Payloads**: Using links that are only active for a limited time to evade detection after scanning.
    - **Emails with Expiring Content**: Creating time-limited access to phishing sites that disappear after a scan period.
    ***
    ### 9. **Bypassing Sandbox and Security Tools**
    - **Fingerprinting Sandbox Environments**: Detecting if the email is being analyzed by automated systems and remaining inactive.
    - **Content Changes Post-Delivery**: Updating links or payloads in an email _after_ it has passed through spam filters.
    - **Using Non-standard Protocols**: Embedding malicious content in lesser-known protocols (e.g., FTP links).
    ***
  - Keep your email Simple.
  - Don't Copy Microsoft or any other emails.
  - Don't Shoot Yourself in the foot!
    - Overtesting.
    - Whitelisting.
  - Know Your Client Time zone!! Don't send thing outside the working time

**8- Learn and Use Tmux ⇒ https://www.youtube.com/watch?v=Yl7NFenTgIo.**

---

### Infrastructure Setup.

- **Creating Your EC2 Instance, Configure the security groups and access it from terminal**
  **\*⇒ Creation Steps**:\*
  Create an AWS Account → Go to Search Bar and Type “EC2” → Hit the first → Choose the Oregon if needed → Click on `Launch Instance` Button → select your Preferred Server to run (Ubuntu would do cool with GoPhish) → Choose what ever you like from Micro → Hit `Launch` → Will ask you to create a new Key pair.. → Choose “Create a new Key Pair” → Name it Whatever you like “_phishing.pem_” → Download it and make sure to not lose it .. 🙂 → Hit `Launch Instance`
  **_⇒_** Configure the security groups **Steps** :
  In the side bar go to `Network & Security Section` → Choose `Security Groups` → Hit `Create New Security Group` → Name it Whatever you want → Description “Configuring Open Ports” → In Inbound Roles Section Hit `Add Role` Button → add Your SSH Port 22 and source 0.0.0.0/0 anywhare-IPv4 → Hit `Add Role` again and Choose Custom UDP and add the port number 53 to allow DNS to work in our server and the source 0.0.0.0/0 anywhare-IPv4 → Hit `Add Role` again and add the port number 80 for the default HTTP port and also the source 0.0.0.0/0 anywhare-IPv4 → Hit `Add Role` again and add the port number 445 for HTTPS and the source 0.0.0.0/0 anywhare-IPv4
  Finally Hit `Add Role` again and add the port number 3333 → this where GoPhish admin panel will running on
  Hit `Create Security Group` → Assign the security group into EC2 Instance by Back to Instance Tab → Right Click on the Instance and choose security → Change security groups → Remove the existence one and add yours…
  _⇒ How To Access Your Server ?_
  ⇒ Using Your Downloaded Key → Hit The terminal and do as follows :
  ```bash
  ~$ mv Downloads/phishing.pem .ssh
  ~$ chmod 600 .ssh/phishing.pem
  ~$ ssh -i .ssh/phishing.pem YourMachineName@iTsIP # Boom You in .
  ```
  ***
- **Setting up Amazon simple email services**
  Go to Search Bar and Type “SES” → Hit the first → go to side bar and choose `Domains` → Hit `Verify New Domain` → Type the Domain That You purchase for your Phishing campaign → Check ☑️ for `Generate DKIM Settings` → Hit `Verify this domain` → Hit `Use Route53` → Hit `Create Record Sets` → Hit `Sending Statistics` → `Edit Your Account Details` → Type For Educational/ testing purpose only, Refresh and you cool!..
  ***
  ### ⇒ Creating S3 Bucket To capture Email Responses:
  Go to side bar and choose `Email Receiving` → Choose `Role Sets` → `Create a New Role set` → Name it Whatever you like → Click the one you just create it and hit `Create Role` → add an recipient email whare it should look legitimate and hit `add recipient` and `Next step` → Now Create Amazon S3 Bucket From the Arrow By Choosing `S3` → `Create New S3` “Make it Unique!” and Hit `Next Step` → Give the Role Name and Be sure that every thing set right → `Create a role` … Go back to `Role Sets` → Choose what you just create and hit `Set As Active Role Set.` | Back to Amazon Route53 Tab and Create MX Record to allow you specifies mail server, inside the Value add `10 inbound-smtp(YourOregon).amazonaws.com` Hit Create Records to make sure that everything is ok:
  ```bash
  ~$ dig Yourdoman.com mx

  ## See The Results ...
  ```
  After That Make Sure that you need to change some SMTP Settings. That's Will allow us to send emails from our fake domains as anyone we want
  Go to `SES Home` → `SMTP Settings` → `Create My SMTP credentials` → `Create` → `Download credentials` and save it …

### Installing GoPhish and Evilginx2 On Our Server.

```bash
~$ sudo apt-get update # Updating our Package
~$ sudo apt-get dist-upgrade # Upgrading ..
~$ sudo apt-get install golang # Installing Golang
~$ go get github.com/gophish/gophish
~$ cd go/src/github.com/gophish/gophish
~$ ls # You Should See gophish.go
~$ go build # Building | Thats will make the gophish file executable and ready to run ..
~$ vim config.json ## To remove the listeng_url from local host to 0.0.0.0:3333 -> Save it and getout..
~$ sudo ./gophish # Now We Starting ..
# => You Going to find Your Gophish credentials in the first terminal msg=
```

Now Go Back To Your Instance and Copy the Public IP of your EC2 and Open Your Browser and Type https://{IP}:3333 → Sign in With The Given `credentials` → Change the default `credentials` .. and now you Cool 🙂

> **_For Installing Evilginx2, Just Follow the Installation steps on this Blog → https://breakdev.org/evilginx-3-3-go-phish/. nothing different than usual._**

- Configuring Evilginx2 on our server.
  ```bash
  ~$ sudo ./bin/evilginx -p phishlets # To Run the tool ..
  ~$ Config domain {YourPhishingDomain.com} # Specify your Domain
  ~$ Config ip {AWSIP} # Type your puplic AWs instance ip
  # At This Stage hit the Route53 from search bar to add another DNS Record. to make domain look like www.microsoft.myphishing.com
  # Hit to Create new record -> Choose whatever the record name based on your target -> type your IP in the Value.
  ~$ phishlets hostname o365 {yourPishingSubDomain} # To chose which phishlets
  ~$ phishlets enable o365 # To enable the phishlets.. Seeing successful output meaning you could to go ..
  ~$ lures create o365
  ~$ lures get-url {theLureNumber} # This will print the link that you should send to the target.
  # Test the URL on yourself before sending anything.
  ~$ sessions # See all the clients with their credentials.
  # This will capture the session cookies too, using any cookies editor extention you will be able to log in.
  ```

---

### Launching your Campaign.

- **Test Before Send!**
  1. Access your AWS Server an Run Gophish
  2. Access The Admin Panel By typing Yor server IP including The Admin panel port `3333`
  3. Head over **_Sending Profile_** and `Name : Whatever you want` | `From : The User You gonna be spofed@YourPhishing.com` | Host*SMTP ServerName*,Username,Pssword ⇒ All that are listed in SES Home ⇒ SMTP Settings and `SMTP credential` that we had created before
  4. Using Send Test email button → Use a temp email .. if it received then you can move to next part
- **Creating GoPhish Campaign**
  1. Hit Users & Groups and import the Email List in bulk(.csv only) and name the group.
  2. Hit the email template and choose a template suitable for your target, write a Catchy Subject, Insert your Phishing login page in this templet(In Words Format).
  3. Landing Page Wouldn't be necessary, Just create one and leave it blank.
  4. Hit The Sending Profiles, Choose a name, add the spoofed personality in`FROM:` @YourPhishingDomain.com, add your SMTP server name attached with :PortNumber in `HOST:` , add your SMTP Creds. hit Save Profile Button.
  5. Campaigns Page : Hit New Campaign, Name it What ever you like, Make sure that you running the evilginx2 as configured, in URL Section add https://{YourAWSip},choose your group and launch ….

---

### References and some resources.

1. https://github.com/PhishyAlice/awesome-phishing
2. https://redfoxsec.com/blog/phishing-simulations-with-gophish/
3. https://help.evilginx.com/
4. https://github.com/An0nUD4Y/Evilginx-Phishing-Infra-Setup
5. https://www.youtube.com/playlist?list=PLxKs1ysVATc9JHJ7w2Uevo2pDAiW1tDBN.
6. https://www.youtube.com/playlist?list=PLVD_SJaedVxnPWPlbJFq98WqA0-OCbM8a ⇒ **_Very Recommended_**.
7. https://fin3ss3g0d.net/index.php/2024/03/04/smishing-with-evilgophish/
8. https://fin3ss3g0d.net/index.php/2024/02/24/qr-code-phishing-with-evilgophish/

---
