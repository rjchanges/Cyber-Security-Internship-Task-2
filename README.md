# Task 2: Phishing Email Analysis

## Objective
[cite_start]To analyze a suspicious email sample, identify its phishing characteristics, and understand the technical and social engineering tactics used by attackers[cite: 55].

## Analysis Report: "Google Job Offer" Phishing Sample

[cite_start]I analyzed a phishing email [cite: 49] [cite_start]and its corresponding headers [cite: 102, 103, 104] to identify indicators of a malicious attack. The analysis confirmed the email was a phishing attempt based on the following evidence:

### 1. Social Engineering & Urgency
* [cite_start]**The Lure:** The email creates a powerful lure by offering a "high-paying position at Google India" [cite: 49] [cite_start]and claiming the candidate was "selected without interview"[cite: 50]. This is highly unusual and designed to make the recipient excited and less critical.
* [cite_start]**Urgent Language:** The email pressures the user with a 12-hour deadline, stating "You must complete verification within 12 hours or the offer will expire"[cite: 50]. This is a classic tactic to rush the victim.

### 2. Sender Spoofing & Impersonation
* [cite_start]The sender address is `hr-team@googIe-careers-jobs.com`[cite: 49]. This is a "typosquatting" attack, using a **capital 'I'** to impersonate the **lowercase 'l'** in "google".
* [cite_start]The "From" name is "Google Careers"[cite: 49], but the email address domain is `googIe-careers-jobs.com`, not the official `google.com`.

### 3. Suspicious Link (Subdomain Attack)
* [cite_start]The verification link is `https://google.com.careers-selection-portal.com/verify`[cite: 50].
* This is a malicious link structure. The **real domain** is `careers-selection-portal.com`, not `google.com`. The attacker has added "google.com" as a **subdomain** to make it look legitimate. A real Google link would have `google.com` as the last part of the domain name (e.g., `careers.google.com`).

### 4. Email Header Analysis (The "Smoking Gun")
The email headers provide definitive technical proof of the attack:
* [cite_start]**Failed Authentication:** The headers clearly show `spf=fail`, `dkim=fail`, and `dmarc=fail`[cite: 103]. [cite_start]This is the mail server's own verification check, confirming that the sender's IP address (`109.185.222.14`) is **not authorized** to send emails on behalf of the domain[cite: 102, 103].
* [cite_start]**Non-Google Server:** The email was `Received: from mailserver92.xyz`[cite: 102]. This is a random, non-Google server, which does not match the "From" address.
* [cite_start]**Mass Mailout:** The `To:` field is set to `undisclosed-recipients:;`[cite: 104], proving this was not a personal email but a mass campaign sent to many people.

---

## Interview Questions & Answers

**1. [cite_start]What is phishing?** [cite: 70]
[cite_start]Phishing is a cyber-attack where attackers impersonate a legitimate person or organization (like Google Careers [cite: 49]) to trick victims into revealing sensitive information, such as login credentials, financial data, or personal identifiers.

**2. [cite_start]How to identify a phishing email?** [cite: 71]
You can identify one by looking for these red flags, all found in this sample:
* [cite_start]**Sender Spoofing:** The "From" email address is misspelled (e.g., `googIe-careers-jobs.com`)[cite: 49].
* [cite_start]**Suspicious Links:** Hovering over links reveals a deceptive domain (e.g., the `google.com.careers...` subdomain trick)[cite: 50].
* [cite_start]**Urgent/Threatening Language:** The email creates a false deadline, like "12 hours or the offer will expire"[cite: 50].
* [cite_start]**Unrealistic Lures:** Offers that are "too good to be true," such as a job at Google "without interview"[cite: 50].
* [cite_start]**Header Failures:** Technical analysis shows failed SPF, DKIM, and DMARC checks[cite: 103].

**3. [cite_start]What is email spoofing?** [cite: 72]
[cite_start]Email spoofing is a technique used to falsify the "From" address of an email[cite: 49]. Attackers do this to make the message appear to come from a trusted source (like Google) to gain the victim's trust. [cite_start]The email headers, however, reveal the true, unauthorized origin[cite: 102].

**4. [cite_start]Why are phishing emails dangerous?** [cite: 73]
They are dangerous because if successful, they can lead to:
* [cite_start]**Credential Theft:** The link `https://google.com.careers-selection-portal.com/verify` [cite: 50] likely leads to a fake login page to steal the user's Google password.
* **Financial Loss:** If an attacker gets your password, they can access saved payment methods or other financial data.
* **Malware Infection:** The link could also have initiated a malicious download.
* **Identity Theft:** The attacker could gain access to your entire digital life.

**5. [cite_start]How can you verify the sender's authenticity?** [cite: 74]
* [cite_start]**Analyze Headers:** Use an email header analyzer [cite: 61] [cite_start]to check for `spf=fail` or `dkim=fail`[cite: 103].
* **Inspect Links:** Hover over all links to see the true destination URL *before* clicking.
* [cite_start]**Check the Domain:** Scrutinize the sender's email domain for misspellings (like the 'I' in `googIe-careers-jobs.com`) [cite: 49] or non-standard extensions.

**6. [cite_start]What tools can analyze email headers?** [cite: 75]
[cite_start]You can use free online tools as suggested by the task brief[cite: 56, 61], such as **MXToolBox** or **G Suite Toolbox (Messageheader)**. Most email clients (like Gmail) also have a "Show original" option to view the raw headers.

**7. [cite_start]What actions should be taken on suspected phishing emails?** [cite: 76]
* **Do NOT** click any links or download attachments.
* **Do NOT** reply to the email.
* **DO** use your email client's "Report Phishing" or "Report Junk" feature.
* **DO** delete the email after reporting it.

**8. [cite_start]How do attackers use social engineering in phishing?** [cite: 77]
Social engineering is the core of phishing. [cite_start]Attackers manipulate human emotions and trust[cite: 80]. In this example:
* [cite_start]**Authority:** They impersonate "Google HR"[cite: 51], a powerful authority figure.
* [cite_start]**Excitement/Greed:** They offer a "high-paying position" [cite: 49] to make the victim excited.
* [cite_start]**Urgency/Fear of Loss:** They create a "12 hours" deadline [cite: 50] to make the victim panic and not think clearly.
