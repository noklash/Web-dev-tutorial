**Cybersecurity Crash Course**  
**3-Session Technical Introduction**

**Level:** Beginner / Early Technical  
**Audience:** Students ages 16–20  
**Prerequisites:** HTML, CSS, JavaScript, basic AI use and prompting

---

### SESSION 1: HOW THE INTERNET AND WEB APPLICATIONS WORK

#### 1.1 The Internet Is a Network of Networks

When you open a website, your computer is communicating with another computer somewhere else on the planet.

A simplified model of what happens:

```
Your device
    ↓
Router / ISP
    ↓
Internet
    ↓
Server
    ↓
Application
    ↓
Database
```

- A **client** is the device or application that requests something.  
- A **server** is a computer or service that provides something.

Example:  
Browser = client  
Instagram’s servers = server  

When you open Instagram, your browser sends requests to Instagram’s servers and receives responses back.

#### 1.2 IP Addresses

Every device communicating over an IP (Internet Protocol) network uses an **IP address**.

Examples:  
- IPv4: `192.168.1.10`  
- IPv6: `2001:db8::1`

Think of an IP address as a network postal address. Your browser ultimately needs one to know where to send traffic.

**Two major types:**

**Private IP addresses** (used inside local networks)  
Common ranges:  
- `192.168.x.x`  
- `10.x.x.x`  
- `172.16.x.x` – `172.31.x.x`

**Public IP addresses**  
Used to identify networks or devices on the public internet.

#### 1.3 DNS (Domain Name System)

You don’t type `142.250.x.x` to visit Google.  
You type `google.com`.

DNS translates human-readable domain names into IP addresses.

Simplified flow:

```
google.com
     ↓
    DNS
     ↓
IP address
     ↓
Google’s server
```

**Try it yourself:**

Linux / macOS:  
```bash
nslookup google.com
# or
dig google.com
```

Windows:  
```bash
nslookup google.com
```

You should see the domain and its associated IP addresses.

#### 1.4 HTTP and HTTPS

Web browsers talk to web servers using **HTTP** (Hypertext Transfer Protocol).  
**HTTPS** is HTTP Secure (encrypted).

A simplified request:

```
GET / HTTP/1.1
Host: example.com
```

Server response:

```
HTTP/1.1 200 OK
Content-Type: text/html
```

Your browser receives the response and renders the page.

Core idea:

```
Browser → HTTP request → Web server → HTTP response → Browser
```

#### 1.5 HTTP Methods

Common methods:

| Method   | Purpose                          | Example          |
|----------|----------------------------------|------------------|
| GET      | Request information              | `GET /profile`   |
| POST     | Send information to the server   | `POST /login`    |
| PUT/PATCH| Modify existing information      | `PATCH /users/123` |
| DELETE   | Request deletion                 | `DELETE /users/123` |

APIs often look like this:

```
GET    /users/123
POST   /users
PATCH  /users/123
DELETE /users/123
```

This matters in cybersecurity because attackers frequently interact with applications simply by crafting and sending requests.

#### 1.6 HTTP Status Codes

You’ve seen `404 Not Found`. Other important ones:

- `200 OK`  
- `301` / `302` Redirect  
- `400 Bad Request`  
- `401 Unauthorized`  
- `403 Forbidden`  
- `404 Not Found`  
- `500 Internal Server Error`

Two critical concepts:

- **Authentication** → “Who are you?”  
- **Authorization** → “What are you allowed to do?”

Example:  
You log into a university portal.  
Authentication: “Yes, you are student123.”  
Authorization: “Student123 can view their own grades but cannot change anyone else’s.”

#### 1.7 Browser Developer Tools

Your browser shows a huge amount of what is happening under the hood.

Open Developer Tools:  
Right-click → Inspect → **Network** tab → Reload the page.

You will see requests for:  
document, stylesheets, JavaScript, images, fonts, API calls, etc.

Click any request and inspect:  
- URL  
- Method  
- Status code  
- Headers  
- Request / Response body  

This is one of the most useful tools for anyone interested in web security.

#### 1.8 Cookies

Websites need ways to remember information about you.  
A **cookie** is a small piece of data the browser stores for a website.

Common uses:  
- Login sessions  
- Preferences  
- Shopping carts  
- Tracking  
- Application state  

Example: `session_id=abc123`

#### 1.9 Sessions

When you log in, the server needs to remember that you are authenticated.

Simplified flow:

```
Username + Password
        ↓
      Server validates
        ↓
   Creates session
        ↓
Browser receives session identifier (usually via cookie)
        ↓
Browser sends the identifier on later requests
        ↓
Server recognises your session
```

If an attacker steals a valid session identifier, they may access the account without knowing the password. This is why session security is critical.

#### 1.10 localStorage and sessionStorage

Web apps can also store data in the browser.

Open Developer Tools → **Application** → Storage  
Look at: Cookies, Local Storage, Session Storage

Key differences:  
- **Cookies** – can be sent automatically with every request  
- **localStorage** – persists until cleared  
- **sessionStorage** – usually lasts only for the tab/session  

Never store sensitive information in browser storage without understanding the security implications.

#### 1.11 Security Starts at the Browser

You have now seen the full chain:

```
DNS → IP → HTTP/HTTPS → Requests → Responses → Cookies → Sessions → Browser storage
```

These are not only web-development concepts — they form the **attack surface** of a web application.

Attackers look for:  
- Weak authentication  
- Bad session handling  
- Poor input validation  
- Exposed information  
- Broken authorization  
- Vulnerable APIs  

---

### SESSION 1 PRACTICAL LABS

**Lab 1 – Explore a Website**  
Use Developer Tools (Network tab). Find:  
1. Main HTML request  
2. A JavaScript file  
3. A CSS file  
4. An image  
5. An API request (if present)  
6. Status code, method, and response headers for each  

**Lab 2 – Explore DNS**  
```bash
nslookup example.com
```
Identify the domain, IP address(es), and the DNS server that answered.

**Lab 3 – Explore Browser Storage**  
Developer Tools → Application → Cookies / Local Storage / Session Storage  
Ask: What information is this site storing about me?  
Do **not** modify or delete anything important.

---

### SESSION 1 CHECKPOINT

You should understand:  
Client • Server • IP address • DNS • HTTP/HTTPS • HTTP methods • Status codes • Authentication • Authorization • Cookies • Sessions • Browser storage • Developer Tools

### SESSION 1 QUIZ

1. What does DNS do?  
   → Translates domain names into IP addresses.

2. Difference between authentication and authorization?  
   → Authentication verifies identity. Authorization determines what that identity is allowed to do.

3. What does HTTP 404 mean?  
   → The requested resource was not found.

4. What is a cookie?  
   → Small data stored by a website in your browser.

5. Why are Developer Tools useful in cybersecurity?  
   → They expose requests, responses, scripts, storage, and other behaviour of web applications.

---

### SESSION 2: IDENTITY, ATTACKS AND SECURE APPLICATIONS

#### 2.1 Authentication

Authentication answers: **“Who are you?”**

Common factors:  
- Something you **know** (password, PIN)  
- Something you **have** (phone, security key)  
- Something you **are** (fingerprint, face)

**MFA (Multi-Factor Authentication)** combines two or more factors and significantly raises the bar for attackers.

#### 2.2 Passwords and Password Hashing

A secure application must **never** store passwords in plain text:

```
username: john
password: football123   ← bad
```

Instead, applications use **password hashing**:

```
Password → Hashing algorithm → Stored hash
```

A good hash is designed to be computationally difficult to reverse.

#### 2.3 Hashing vs Encryption vs Encoding

These are often confused:

| Concept     | Direction          | Purpose                          | Reversible?      |
|-------------|--------------------|----------------------------------|------------------|
| Hashing     | One-way            | Password storage, integrity      | No (by design)   |
| Encryption  | Two-way with key   | Confidentiality                  | Yes (with key)   |
| Encoding    | Representation     | Data format (e.g. Base64)        | Yes (anyone can) |

Encoding is **not** encryption or security.

#### 2.4 Hash Demonstration

Linux / macOS:  
```bash
echo -n "hello" | sha256sum
echo -n "Hello" | sha256sum
```

Notice that changing one character produces a completely different hash.

**Important:** SHA-256 is **not** recommended for password storage.  
Use dedicated algorithms designed to be slow and memory-hard:  
**Argon2**, **bcrypt**, **scrypt**.

#### 2.5 Brute-Force and Dictionary Attacks

If an attacker obtains password hashes, they can try common passwords (dictionary attack) or every possible combination (brute force).

Defences go beyond “make the password complicated”:  
- Long, unique passwords  
- Strong password hashing  
- Rate limiting  
- Account lockouts / progressive delays  
- MFA  

#### 2.6 Phishing

Phishing tricks a person into revealing information or performing an unsafe action.

Classic pattern:  
Fear → Urgency → Click → Fake login page → Credentials stolen

#### 2.7 URL Anatomy

```
https://login.example.com/account?id=123
```

- `https://` → Protocol  
- `login` → Subdomain  
- `example.com` → Domain  
- `/account` → Path  
- `?id=123` → Query parameter  

Dangerous example:  
`https://instagram.com.security.example.com`  

The real domain is still **example.com**. The word “instagram” appearing earlier does not make it Instagram.

#### 2.8 Smishing

Phishing delivered via SMS / text messages.

Warning signs: unexpected message, urgency, payment request, suspicious short links, requests for personal data.

#### 2.9 Social Engineering

Attacks that target human psychology rather than pure technology.

Attackers exploit: fear, curiosity, authority, greed, trust, urgency, sympathy.

Even a technically perfect system can be compromised if an authorised user is convinced to hand over access.

#### 2.10 Cross-Site Scripting (XSS)

XSS occurs when a web application handles user-controlled input unsafely, allowing attacker-controlled script to run in another user’s browser.

Unsafe example:  
```js
output.innerHTML = userInput;   // dangerous
```

Safer for plain text:  
```js
output.textContent = userInput; // treats value as text
```

#### 2.11 Why XSS Matters

If a platform displays usernames or comments without proper handling, an attacker can inject code that runs for other users. Possible outcomes include page manipulation, actions performed as the victim, theft of sensitive data (under certain conditions), or phishing from a trusted site.

#### 2.12 Input Validation & Output Encoding

Never trust user input. Users can submit: normal text, numbers, HTML, JavaScript, unexpected characters, extremely long values, or malformed data.

Applications must:  
1. Validate input (structure, length, allowed characters)  
2. Encode output safely  
3. Use safe APIs  

Validation alone is not enough.

#### 2.13 Authorization Bugs & IDOR

Example university API:  
`GET /students/123/grades`

Student 123 should only see their own grades.  
If changing the number to `/students/124/grades` returns another student’s data, the application has a serious authorization failure (often called **IDOR** – Insecure Direct Object Reference, part of broken access control).

**Only test this against systems you own or have explicit written permission to test.**

---

### SESSION 2 PRACTICAL LABS

**Lab 1 – Hashing**  
Generate hashes for: `hello`, `Hello`, `hello1`, `hello123` and observe the differences.

**Lab 2 – Secure Input Handling**  
Create a local HTML page with an input and output div.  
Compare `innerHTML` vs `textContent` and understand why the latter is safer for untrusted plain text.

**Lab 3 – Inspect Authentication**  
Use a local app or deliberately vulnerable training environment (never real accounts you don’t own).  
Identify the login request, method, response, cookies, and session information.

---

### SESSION 2 CHECKPOINT

You should understand:  
Authentication • MFA • Password hashing • Encryption vs Encoding • Brute-force & dictionary attacks • Phishing • Smishing • Social engineering • URL structure • XSS • Input validation • Authorization • IDOR

### SESSION 2 QUIZ

1. What does authentication answer? → “Who are you?”  
2. What does authorization answer? → “What are you allowed to do?”  
3. Is Base64 encryption? → No, it is encoding.  
4. What does XSS stand for? → Cross-Site Scripting.  
5. Why is `textContent` safer than `innerHTML` for untrusted plain text? → It treats the value as text instead of parsing it as HTML.

---

### SESSION 3: NETWORK SECURITY, MALWARE, DEFENCE AND CAREERS

#### 3.1 Ports

A computer can run many network services at once. **Ports** identify the communication endpoint for each service.

Common ports:  
- 22 → SSH  
- 53 → DNS  
- 80 → HTTP  
- 443 → HTTPS  

Full address example: `192.168.1.10:443`

#### 3.2 TCP and UDP

- **TCP** – reliable, connection-oriented (connect → send → confirm)  
- **UDP** – connectionless, lower overhead (send and hope)

Both are useful depending on the application’s needs.

#### 3.3 Listening Services

On Linux:  
```bash
ss -tuln
```

A line such as `0.0.0.0:22` means something is listening on port 22.  
Security question: Should this service actually be exposed to the network?

#### 3.4 Attack Surface

The **attack surface** is every possible point an attacker can interact with a system: web application, SSH, APIs, email, VPN, database, user accounts, cloud services, etc.

Reducing unnecessary exposure reduces risk.

#### 3.5 Firewalls

A firewall enforces rules about what traffic is allowed:

```
Internet → Firewall → Server
```

Example rules: Allow TCP 443, Allow TCP 22 only from trusted networks, Block everything else.  
A firewall is one layer — it does not automatically make an application secure.

#### 3.6 Malware Types

- **Trojan** – disguised as legitimate software  
- **Worm** – spreads between systems  
- **Ransomware** – encrypts data and demands payment  
- **Spyware** – secretly collects information  
- **Botnet** – group of compromised devices controlled by an attacker

#### 3.7 How Malware Enters

Common paths: phishing → malicious attachment → execution; fake software → user installs it; vulnerable software → attacker exploits it.

Cybersecurity is a chain:  
Phishing → stolen credentials → authentication bypassed → access gained → system / data compromised.

#### 3.8 Vulnerabilities

A **vulnerability** is a weakness that could be exploited: weak passwords, outdated software, poor input validation, broken authorization, misconfigured cloud storage, excessive permissions, exposed services, insecure APIs.

#### 3.9 Threat, Vulnerability, Risk

- **Threat** – something capable of causing harm (attacker, malware)  
- **Vulnerability** – a weakness (weak password)  
- **Risk** – the potential that the threat will exploit the vulnerability and cause harm

#### 3.10 Least Privilege

Give users and programs only the permissions they actually need.  
If an account is compromised, limited privileges limit the damage.

#### 3.11 Logs

Systems generate continuous event records: successful/failed logins, file access, password changes, new devices, etc.

A suspicious pattern might look like:  
multiple failed logins → successful login → password change → recovery email change → new device → large download.

#### 3.12 Incident Response

Simplified lifecycle:  
Detect → Investigate → Contain → Eradicate → Recover → Learn

#### 3.13 SIEM

**SIEM** (Security Information and Event Management) systems collect and analyse logs from many sources so analysts can spot patterns that indicate compromise.

#### 3.14 Threat Modelling

Think about security **before** something goes wrong.  
For a student portal, list: Assets, Threats, Vulnerabilities, and Controls (MFA, input validation, access controls, logging, encryption, updates, backups).

#### 3.15 Build a Secure Student Portal (Project)

Using HTML, CSS and JavaScript, create a local-only fictional student portal with:  
Login → MFA → Dashboard → Profile → Grades  

Two roles: `student` and `admin`.  

Security requirements:  
- Authentication (username + password + MFA code)  
- Authorization (students cannot reach `/admin`)  
- Safe input handling  
- Simple logging (timestamp, username, success/failure, action)  
- Basic rate-limiting concept for login attempts  

#### 3.16 Security Investigation Challenge

Given this log sequence:  
```
09:12 Failed login: student01 (×4)
09:14 Successful login: student01
09:14 Password changed
09:15 Recovery email changed
09:16 New device added
09:17 Large file download
```

Questions:  
1. What likely happened?  
2. What should you investigate?  
3. What should happen immediately?

#### 3.17 Cybersecurity Career Paths

Cybersecurity is not one job. Common paths include:

- **Security Operations (SOC Analyst)** – monitoring, logs, SIEM, incident response  
- **Penetration Testing** – authorised vulnerability testing  
- **Application Security** – securing software during development (your web skills transfer directly)  
- **Cloud Security** – protecting cloud infrastructure and IAM  
- **Digital Forensics** – investigating evidence after incidents  
- **Incident Response** – containing and recovering from attacks  
- **Security Engineering** – building secure systems by design  
- **GRC** (Governance, Risk & Compliance) – policies, risk, auditing, regulations  

---

### SESSION 3 PRACTICAL LABS

**Lab 1** – Inspect listening services with `ss -tuln` and ask which are necessary.  
**Lab 2** – Create or review a local log file and look for suspicious patterns.  
**Lab 3** – Threat-model your student portal (Asset | Threat | Vulnerability | Control).

---

### FINAL CYBERSECURITY CHECKPOINT

You should now be able to explain and, more importantly, **connect**:

DNS • IP addresses • HTTP/HTTPS • TCP/UDP • Ports • Cookies • Sessions • Authentication • Authorization • MFA • Hashing • Encryption • Phishing • Social engineering • XSS • Input validation • Vulnerabilities • Malware • Firewalls • Logs • SIEM • Incident response • Threat modelling • Least privilege

Example chain of thinking:  
Phishing → stolen password → authentication bypassed → account accessed → recovery email changed → victim loses control → logs reveal the activity → incident response begins.

That is cybersecurity thinking.

---

### FINAL SELF-ASSESSMENT

Rate each area 1–5 (interest / aptitude):  
Web Security • Networking • Programming / Secure Coding • Investigation • Infrastructure • Offensive Security • Defensive Security • Security Engineering

---

### WHERE TO GO NEXT

Follow the path that interests you most:  
- Web Security → HTTP, JavaScript, APIs, Authentication, OWASP, web labs  
- Networking → TCP/IP, DNS, routing, firewalls, Linux networking  
- Infrastructure → Linux, processes, filesystems, containers, cloud  
- Investigation → Logs, SIEM, digital forensics, incident response  
- Application Security → Programming, OWASP, vulnerability research  

Or start with the universal foundations:  
Linux + Networking + Programming + Operating Systems + Web Technologies + Security Fundamentals  

These transfer into almost every specialisation.

---

### THE CORE IDEA

Cybersecurity is the discipline of understanding:

How systems work → How they can fail → How they can be attacked → How attacks can be detected → How systems can be defended → How systems can be designed more securely from the start.

You do not need to choose a career today.  
After these three sessions you should be able to ask a much better question:

**“Which part of cybersecurity do I actually want to get good at?”**
