Cybersecurity Crash Course

3-Session Technical Introduction

Level: Beginner / Early Technical
Audience: Students ages 16–20
Prerequisites: HTML, CSS, JavaScript, basic AI use and prompting

⸻

SESSION 1: HOW THE INTERNET AND WEB APPLICATIONS WORK

1.1 The Internet Is a Network of Networks

When you open a website, your computer is communicating with another computer somewhere else.

A simplified model:

Your device
    ↓
Router
    ↓
Internet
    ↓
Server
    ↓
Application
    ↓
Database

A client is the device or application requesting something.

A server is a computer or service providing something.

For example:

Browser = client
Instagram server = server

When you open Instagram, your browser sends requests to Instagram’s servers and receives responses.

⸻

1.2 IP Addresses

Every device communicating over an IP (Internet Protocol) network uses an IP address.

Example:

192.168.1.10

or an IPv6 address such as:

2001:db8::1

Think of an IP address as a network address.

Your browser ultimately needs an address to know where to send network traffic.

There are two major types:

Private IP addresses

Used inside local networks.

Common ranges include:

192.168.x.x
10.x.x.x
172.16.x.x - 172.31.x.x

Public IP addresses

Used to identify networks or devices communicating across the public internet.

⸻

1.3 DNS

You don’t normally type:

142.250.x.x

to access Google.

You type:

google.com

DNS (Domain Name System) translates domain names into IP addresses.

Simplified:

google.com
     ↓
    DNS
     ↓
IP address
     ↓
Google server

Try it.

Linux / macOS

nslookup google.com

or:

dig google.com

Windows

nslookup google.com

You should see information about the domain and its associated addresses.

⸻

1.4 HTTP and HTTPS

Web browsers communicate with web servers using HTTP (Hypertext Transfer Protocol).

HTTPS means HTTP Secure.

A simplified web request looks like:

GET / HTTP/1.1
Host: example.com

The server sends a response:

HTTP/1.1 200 OK
Content-Type: text/html

Your browser receives the response and renders the page.

The important idea:

Browser
   ↓
HTTP request
   ↓
Web server
   ↓
HTTP response
   ↓
Browser

⸻

1.5 HTTP Methods

Common HTTP methods include:

GET

Request information.

GET /profile

POST

Send information to the server.

POST /login

PUT / PATCH

Modify existing information.

DELETE

Request deletion of something.

For example, an API (Application Programming Interface) might have:

GET    /users/123
POST   /users
PATCH  /users/123
DELETE /users/123

This becomes important in cybersecurity because attackers often interact with applications by sending requests.

⸻

1.6 HTTP Status Codes

You’ve probably seen:

404 Not Found

Other important codes:

200 OK
301 Redirect
302 Redirect
400 Bad Request
401 Unauthorized
403 Forbidden
404 Not Found
500 Internal Server Error

Two especially important concepts:

Authentication

Who are you?

Authorization

What are you allowed to do?

Example:

You successfully log into a university system.

Authentication:

“Yes, you are student123.”

Authorization:

“Student123 can view their grades but cannot modify another student’s grades.”

⸻

1.7 Browser Developer Tools

Your browser exposes a lot of what is happening underneath a website.

Open Developer Tools:

Right click → Inspect

Then open:

Network

Reload a website.

You will see requests such as:

document
stylesheet
JavaScript
images
API requests
fonts

Click one request and inspect:

* URL
* Method
* Status
* Headers
* Request data
* Response

This is one of the most useful tools you can learn as someone interested in web security.

⸻

1.8 Cookies

Websites need ways to remember information about you.

A cookie is a small piece of data stored by the browser for a website.

Cookies can be used for:

* Login sessions
* Preferences
* Shopping carts
* Tracking
* Other application state

You might see something like:

session_id=abc123

⸻

1.9 Sessions

When you log into a website, the server needs to remember that you’re authenticated.

A simplified process:

Username + Password
        ↓
      Server
        ↓
   Credentials valid
        ↓
 Create session
        ↓
Browser receives session identifier
        ↓
Browser sends session identifier
        ↓
Server recognises your session

This is why session security matters.

If an attacker obtains a valid session, they may potentially access the account without knowing the original password.

⸻

1.10 localStorage and sessionStorage

Web applications can also store information in browser storage.

Open Developer Tools:

Application → Storage

Look at:

Cookies
Local Storage
Session Storage

The important difference:

* Cookies: Can be sent automatically with web requests.
* localStorage: Data remains in the browser until removed.
* sessionStorage: Data generally lasts for the browser tab/session.

Don’t store sensitive information in browser storage without understanding the security implications.

⸻

1.11 Security Starts at the Browser

You’ve now seen:

DNS
 ↓
IP
 ↓
HTTP/HTTPS
 ↓
Requests
 ↓
Responses
 ↓
Cookies
 ↓
Sessions
 ↓
Browser storage

These aren’t just web-development concepts.

They are part of the attack surface of a web application.

An attacker may look for:

* Weak authentication
* Bad session handling
* Poor input validation
* Exposed information
* Broken authorization
* Vulnerable APIs

⸻

SESSION 1 PRACTICAL LAB

Lab 1: Explore a Website

Use your browser Developer Tools.

Find:

1. The main HTML request.
2. A JavaScript file.
3. A CSS file.
4. An image request.
5. An API request if one exists.
6. The HTTP status code for each.
7. The request method.
8. The response headers.

⸻

Lab 2: Explore DNS

Run:

nslookup example.com

Identify:

* Domain
* IP address
* DNS server responding to your request

⸻

Lab 3: Explore Your Browser

Open:

Developer Tools
→ Application
→ Cookies
→ Local Storage
→ Session Storage

Ask yourself:

What information is this website storing in my browser?

Do not modify or delete anything important.

⸻

SESSION 1 CHECKPOINT

You should now understand:

* Client
* Server
* IP address
* DNS
* HTTP
* HTTPS
* HTTP methods
* HTTP status codes
* Authentication
* Authorization
* Cookies
* Sessions
* Browser storage
* Developer Tools

⸻

SESSION 1 QUIZ

1. What does DNS do?

Answer: Translates domain names into IP addresses.

2. What is the difference between authentication and authorization?

Answer: Authentication verifies who you are. Authorization determines what you’re allowed to access or do.

3. What does HTTP 404 mean?

Answer: The requested resource was not found.

4. What is a cookie?

Answer: Data stored by a website in your browser.

5. Why are Developer Tools useful to cybersecurity students?

Answer: They expose requests, responses, scripts, storage and other behaviour occurring inside web applications.

⸻

SESSION 2: IDENTITY, ATTACKS AND SECURE APPLICATIONS

2.1 Authentication

Authentication answers:

Who are you?

Common authentication factors include:

Something you know

Password or PIN.

Something you have

Phone, security key or authentication device.

Something you are

Fingerprint or face.

MFA (Multi-Factor Authentication) combines multiple authentication factors.

⸻

2.2 Passwords and Password Hashing

A secure application shouldn’t store passwords like:

username: john
password: football123

If attackers obtain the database, they immediately have the passwords.

Instead, applications should use password hashing.

Simplified:

Password
   ↓
Password hashing algorithm
   ↓
Stored hash

A hash is designed to be computationally difficult to reverse.

⸻

2.3 Hashing vs Encryption vs Encoding

These are different concepts.

Hashing

Generally one-way.

data → hash

Used for things such as password verification and integrity checks.

Encryption

Designed to be reversible with the appropriate key.

plaintext
   ↓
encryption + key
   ↓
ciphertext
   ↓
decryption + key
   ↓
plaintext

Encoding

Changes data into another representation.

Example:

text → Base64

Encoding is not encryption.

Anyone who knows the encoding can decode it.

⸻

2.4 Hash Demonstration

On Linux:

echo -n "hello" | sha256sum

Now:

echo -n "Hello" | sha256sum

Notice how changing one character produces a completely different hash.

You can also experiment with:

echo -n "password123" | sha256sum

Important:

SHA-256 is not the recommended way to store passwords.

Modern password storage should use dedicated password hashing algorithms such as:

* Argon2
* bcrypt
* scrypt

These are deliberately designed to make password guessing more expensive.

⸻

2.5 Brute Force and Dictionary Attacks

Suppose an attacker obtains a password hash.

They might try:

password
123456
password123
qwerty
football
...

and hash each guess.

This is a simplified dictionary attack.

A brute-force attack systematically tries combinations.

The defence is not simply:

“Make the password complicated.”

Better defences include:

* Long passwords
* Unique passwords
* Strong password hashing
* Rate limiting
* MFA

⸻

2.6 Phishing

Phishing is an attack designed to trick you into revealing information or performing an unsafe action.

Example:

Your university account will be deleted.
Verify immediately:
https://example-security-login.com

The attacker is trying to create:

Fear
 ↓
Urgency
 ↓
Click
 ↓
Fake login
 ↓
Credentials stolen

⸻

2.7 URL Anatomy

Consider:

https://login.example.com/account?id=123

Break it down:

https://

Protocol

login

Subdomain

example.com

Domain

/account

Path

?id=123

Query parameter

Now consider:

https://instagram.com.security.example.com

The actual domain is:

example.com

The fact that the word “instagram” appears earlier doesn’t make it Instagram.

⸻

2.8 Smishing

Smishing is phishing through SMS or text messaging.

Example:

Your package is waiting.
Pay ₦1,500 to reschedule:
https://short-link.example

Warning signs:

* Unexpected message
* Urgency
* Payment request
* Suspicious link
* Request for personal information

⸻

2.9 Social Engineering

Social engineering attacks the human decision-making process.

Attackers exploit:

* Fear
* Curiosity
* Authority
* Greed
* Trust
* Urgency
* Sympathy

A technically secure system can still be compromised if someone convinces an authorised user to hand over access.

⸻

2.10 XSS

XSS (Cross-Site Scripting) occurs when a web application handles user-controlled input unsafely, allowing unintended script content to execute in a user’s browser.

Consider:

<input id="name">
<div id="output"></div>

Unsafe JavaScript:

const name = document.getElementById("name").value;
document.getElementById("output").innerHTML = name;

The problem is that innerHTML tells the browser to interpret the value as HTML.

A safer approach for plain text is:

document.getElementById("output").textContent = name;

Now the browser treats the value as text.

⸻

2.11 Why XSS Matters

Imagine a social platform displaying:

Username:
[ user input ]

If the application handles that input incorrectly, an attacker could potentially cause code to execute in another user’s browser.

Possible consequences can include:

* Manipulating the page
* Performing actions as the user
* Stealing sensitive information under certain conditions
* Phishing users through a trusted website

This is why input handling matters.

⸻

2.12 Input Validation

Never assume user input is safe.

Users can submit:

normal text
numbers
HTML
JavaScript
unexpected characters
extremely long values
malformed data

Applications should validate and safely handle input.

Examples:

Age → should be a valid number
Email → should follow expected structure
Username → should follow allowed character rules

But validation alone isn’t enough.

Applications also need appropriate output encoding and safe APIs.

⸻

2.13 Authorization Bugs

Imagine a university API:

GET /students/123/grades

Student 123 should only see their own grades.

What if changing the number to:

GET /students/124/grades

returns another student’s grades?

That’s a serious authorization problem.

The application is failing to properly enforce:

Who is allowed to access this resource?

This type of issue is commonly associated with IDOR (Insecure Direct Object Reference) and broader broken access control.

Only test this concept against applications you own or are explicitly authorised to test.

⸻

SESSION 2 PRACTICAL LAB

Lab 1: Hashing

Generate hashes for:

hello
Hello
hello1
hello123

Observe the differences.

⸻

Lab 2: Secure Input Handling

Build a local HTML page with:

<input id="name">
<button id="submit">Submit</button>
<div id="output"></div>

Implement both:

output.innerHTML = name;

and:

output.textContent = name;

Understand why the second approach is safer when displaying untrusted plain text.

⸻

Lab 3: Inspect Authentication

Use a local application or a deliberately vulnerable training environment.

Identify:

* Login request
* HTTP method
* Response
* Cookies
* Session information
* Authentication state

Do not attempt this against accounts or systems you don’t own.

⸻

SESSION 2 CHECKPOINT

You should now understand:

* Authentication
* MFA
* Password hashing
* Encryption
* Encoding
* Brute force
* Dictionary attacks
* Phishing
* Smishing
* Social engineering
* URL structure
* XSS
* Input validation
* Authorization
* IDOR

⸻

SESSION 2 QUIZ

1. What does authentication answer?

Answer: “Who are you?”

2. What does authorization answer?

Answer: “What are you allowed to do?”

3. Is Base64 encryption?

Answer: No. Base64 is encoding.

4. What does XSS stand for?

Answer: Cross-Site Scripting.

5. Why is textContent generally safer than innerHTML for displaying untrusted plain text?

Answer: textContent treats the supplied value as text rather than parsing it as HTML.

⸻

SESSION 3: NETWORK SECURITY, MALWARE, DEFENCE AND CYBERSECURITY CAREERS

3.1 Ports

A computer can run multiple network services.

Ports identify communication endpoints for those services.

Common examples:

22    SSH
53    DNS
80    HTTP
443   HTTPS

An address can therefore be thought of as:

192.168.1.10:443

Where:

192.168.1.10 = IP address
443           = port

⸻

3.2 TCP and UDP

TCP (Transmission Control Protocol) provides reliable, connection-oriented communication.

UDP (User Datagram Protocol) is connectionless and generally has lower communication overhead.

Simplified:

TCP

Connect
 ↓
Send
 ↓
Confirm
 ↓
Continue

UDP

Send
 ↓
No built-in delivery confirmation

Both are useful depending on the application.

⸻

3.3 Listening Services

A service can listen for incoming network connections.

On Linux:

ss -tuln

You might see:

LISTEN
0.0.0.0:22

This means something is listening for connections on port 22.

The security question becomes:

Should this service actually be exposed?

Every unnecessary exposed service increases the attack surface.

⸻

3.4 Attack Surface

The attack surface is the collection of possible points where an attacker could interact with a system.

For a university server, this might include:

Web application
SSH
APIs
Email
VPN
Database
User accounts
Cloud services

Reducing unnecessary exposure reduces opportunities for attack.

⸻

3.5 Firewalls

A firewall controls network traffic according to rules.

Think:

Internet
   ↓
Firewall
   ↓
Server

Example rules:

Allow TCP 443
Allow TCP 22 from trusted network
Block everything else

A firewall is one layer of defence.

It does not magically make an application secure.

⸻

3.6 Malware

Malware means malicious software.

Trojan

Malicious software disguised as legitimate software.

Worm

Malware capable of spreading between systems.

Ransomware

Malware that restricts access to data or systems and demands payment.

Spyware

Software designed to secretly collect information.

Botnet

A collection of compromised devices controlled by an attacker.

⸻

3.7 How Malware Gets In

Common paths include:

Phishing
   ↓
Malicious attachment
   ↓
User opens it
   ↓
Malware executes

Or:

Fake software
   ↓
User installs it
   ↓
Malware executes

Or:

Vulnerable software
   ↓
Attacker exploits vulnerability
   ↓
Malware or unauthorised access

Cybersecurity is therefore connected:

Phishing
   ↓
Credentials
   ↓
Authentication
   ↓
Access
   ↓
System
   ↓
Data

⸻

3.8 Vulnerabilities

A vulnerability is a weakness that could potentially be exploited.

Examples:

* Weak passwords
* Outdated software
* Poor input validation
* Broken authorization
* Misconfigured cloud storage
* Excessive permissions
* Exposed services
* Insecure APIs

⸻

3.9 Threat, Vulnerability and Risk

These concepts are often confused.

Threat

Something capable of causing harm.

Example:

Attacker

Vulnerability

A weakness.

Example:

Weak password

Risk

The potential for the threat to exploit the vulnerability and cause harm.

Threat
  +
Vulnerability
  ↓
Risk

⸻

3.10 Least Privilege

Give users and programs only the permissions they need.

Example:

A student account should be able to:

View own grades
View courses
Submit assignments

It should not be able to:

Delete university users
Modify grades
Access server configuration

If the account is compromised, limiting permissions limits potential damage.

⸻

3.11 Logs

Systems constantly generate events.

Examples:

Login successful
Login failed
File accessed
Connection accepted
Connection rejected
Password changed
New device added

A simplified log:

10:01 Login failed
10:01 Login failed
10:02 Login failed
10:02 Login failed
10:03 Login successful
10:03 Password changed
10:04 Recovery email changed
10:05 New device added

This should immediately attract attention.

⸻

3.12 Incident Response

Incident response is the process of dealing with a security incident.

A simplified lifecycle:

Detect
  ↓
Investigate
  ↓
Contain
  ↓
Eradicate
  ↓
Recover
  ↓
Learn

Example:

Someone gains access to a student account.

Detect

Suspicious login discovered.

Investigate

Determine what happened.

Contain

Terminate sessions and secure the account.

Eradicate

Remove the attacker’s access.

Recover

Restore normal account operation.

Learn

Determine how to prevent recurrence.

⸻

3.13 SIEM

SIEM (Security Information and Event Management) systems collect and analyse logs from multiple systems.

Simplified:

Servers ───────┐
               │
Applications ──┤
               │
Firewalls ─────┤
               ↓
              SIEM
               ↓
       Security Analyst

A security analyst might investigate:

Thousands of failed logins
        +
Successful login
        +
Unusual location
        +
New device

This could indicate account compromise.

⸻

3.14 Threat Modelling

Threat modelling means thinking about security before something goes wrong.

For a student portal:

Assets

What are we protecting?

Student accounts
Grades
Personal information
Course material
Financial information

Threats

Who or what could cause harm?

Criminal
Malicious insider
Automated attacker
Compromised account

Vulnerabilities

What could go wrong?

Weak passwords
XSS
Broken authorization
Outdated software
Exposed API

Controls

What can reduce the risk?

MFA
Input validation
Access controls
Logging
Encryption
Updates
Backups

⸻

3.15 Build a Secure Student Portal

Use your HTML, CSS and JavaScript skills.

Create a local-only fictional student portal.

Features

Login
 ↓
MFA
 ↓
Dashboard
 ↓
Profile
 ↓
Grades

Create two roles:

student
admin

⸻

Security requirements

Authentication

Require:

Username
Password
MFA code

Authorization

A student should not access:

/admin

Input handling

Safely display user-provided information.

Logging

Record:

Timestamp
Username
Success/Failure
Action

Rate limiting concept

Ask:

What happens if someone sends 10,000 login requests?

Implement a simple local demonstration that limits repeated login attempts.

⸻

3.16 Security Investigation Challenge

Given:

09:12 Failed login: student01
09:12 Failed login: student01
09:13 Failed login: student01
09:13 Failed login: student01
09:14 Successful login: student01
09:14 Password changed
09:15 Recovery email changed
09:16 New device added
09:17 Large file download

Answer:

1. What happened?

Possible account compromise.

2. What should you investigate?

* Source IP
* Device
* Login location
* Authentication events
* Password change
* Recovery information
* Sessions
* Downloaded files
* Other account activity

3. What should happen immediately?

Contain the account and prevent further unauthorised access.

⸻

3.17 Cybersecurity Career Paths

Cybersecurity is not one job.

Security Operations

SOC (Security Operations Center) Analyst

Monitors systems and investigates suspicious activity.

Learn:

Linux
Networking
Logs
SIEM
Incident response

⸻

Penetration Testing

Tests systems for vulnerabilities with permission.

Learn:

Linux
Networking
Web applications
Programming
Security testing

⸻

Application Security

Secures software during development.

Learn:

JavaScript
APIs
Authentication
Authorization
Secure coding
Web vulnerabilities

Your existing web-development knowledge transfers directly here.

⸻

Cloud Security

Protects infrastructure running on cloud platforms.

Learn:

Linux
Networking
Cloud platforms
IAM
Containers
Automation

IAM means Identity and Access Management, the systems and policies used to control who can access what.

⸻

Digital Forensics

Investigates digital evidence after incidents.

Learn:

Operating systems
Filesystems
Logs
Networking
Evidence handling

⸻

Incident Response

Investigates and contains security incidents.

Learn:

Logs
Networking
Operating systems
Malware
Investigation
Automation

⸻

Security Engineering

Builds systems that are secure by design.

Learn:

Programming
Linux
Networking
Cloud
Infrastructure
Cryptography
Automation
Architecture

⸻

GRC

GRC means Governance, Risk and Compliance.

Focuses on:

Risk
Policies
Security controls
Auditing
Regulations
Compliance

Less programming, more organisational security.

⸻

SESSION 3 PRACTICAL LABS

Lab 1: Inspect Network Services

On Linux:

ss -tuln

Identify:

* Listening ports
* TCP services
* UDP services

Ask:

Which services are actually necessary?

⸻

Lab 2: Investigate Logs

Create or inspect a local log containing:

login success
login failure
password change
new device
file access

Look for suspicious patterns.

⸻

Lab 3: Threat Model Your Student Portal

Create four columns:

Asset	Threat	Vulnerability	Control
Student account	Account takeover	Weak password	MFA
Grades	Unauthorized modification	Broken authorization	Access control
Login	Brute force	Unlimited attempts	Rate limiting
User input	XSS	Unsafe HTML insertion	Safe output handling

⸻

FINAL CYBERSECURITY CHECKPOINT

You should now be able to explain:

DNS
IP addresses
HTTP/HTTPS
TCP/UDP
Ports
Cookies
Sessions
Authentication
Authorization
MFA
Hashing
Encryption
Phishing
Social engineering
XSS
Input validation
Vulnerabilities
Malware
Firewalls
Logs
SIEM
Incident response
Threat modelling
Least privilege

More importantly, you should be able to connect them.

For example:

Phishing
   ↓
Stolen password
   ↓
Authentication bypassed
   ↓
Account accessed
   ↓
Attacker changes recovery email
   ↓
Victim loses account
   ↓
Logs reveal suspicious activity
   ↓
Incident response begins

That is cybersecurity thinking.

⸻

FINAL SELF-ASSESSMENT

Rate each from 1–5.

Web Security

How interested are you in understanding how websites and APIs can be attacked and defended?

Networking

Do IP addresses, DNS, ports and protocols interest you?

Programming

Do you enjoy finding and fixing security problems in code?

Investigation

Would you enjoy analysing logs and figuring out what happened?

Infrastructure

Do Linux, servers, cloud systems and networks interest you?

Offensive Security

Do you enjoy thinking:

“If I were an attacker, where would this system be weak?”

Defensive Security

Do you enjoy thinking:

“How do I make this system harder to attack?”

Security Engineering

Do you enjoy building systems with security controls from the beginning?

⸻

WHERE TO GO NEXT

If web security interested you most:

HTTP
 ↓
JavaScript
 ↓
APIs
 ↓
Authentication
 ↓
OWASP
 ↓
Web security labs

If networking interested you:

TCP/IP
 ↓
DNS
 ↓
Routing
 ↓
Firewalls
 ↓
Linux networking
 ↓
Network security

If Linux and infrastructure interested you:

Linux
 ↓
Processes
 ↓
Filesystems
 ↓
Networking
 ↓
Permissions
 ↓
Containers
 ↓
Cloud
 ↓
Cloud security

If investigation interested you:

Linux
 ↓
Logs
 ↓
Networking
 ↓
SIEM
 ↓
Digital forensics
 ↓
Incident response

If breaking and fixing applications interested you:

Programming
 ↓
Web applications
 ↓
APIs
 ↓
OWASP
 ↓
Vulnerability research
 ↓
Application security

If all of it interested you:

Start with the fundamentals.

Linux
+
Networking
+
Programming
+
Operating Systems
+
Web Technologies
+
Security Fundamentals

Those foundations transfer into almost every cybersecurity specialization.

⸻

THE CORE IDEA

Cybersecurity is the discipline of understanding:

How systems work
        ↓
How systems can fail
        ↓
How systems can be attacked
        ↓
How attacks can be detected
        ↓
How systems can be defended
        ↓
How systems can be designed more securely

You don’t need to decide your cybersecurity career today.

After these three sessions, you should have enough exposure to ask a much better question:

“Which part of cybersecurity do I actually want to get good at?”