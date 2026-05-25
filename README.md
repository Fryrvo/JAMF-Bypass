
# Jamf DNS Bypass (Pc-Less & Free)

A simple, lightweight method to block Jamf MDM profiles from checking in or enforcing restrictions on devices. This method **does not require a PC**, paid tools, or jailbreaking/rooting. It works purely at the network layer by cutting off communication to management servers.

> ⚠️ **Privacy Notice:** 
We do not recommend using demo DNS profile 
To protect your data privacy and prevent bandwidth logs from being collected
It highly recommended use your own private configuration via trusted providers like NextDNS or local tools like Pi-hole.

## How It Works
When a managed device boots up or connects to the internet, it pings specific Apple and Jamf servers to pull down restrictions. By using a custom DNS layer, we drop those requests before they ever reach the device, rendering the management profiles inactive.



## Self Hosted Setup Instructions

### Method A: NextDNS (Recommended for Mobile/Individual Devices)
1. Go to [NextDNS](https://nextdns.io) and create a free account.
2. In your dashboard, navigate to the **Denylist** tab.
3. Copy the domains from the `blocklists/jamf-domains.txt` file in this repository and paste them in.
4. Go to the **Setup** tab on NextDNS, download the configuration profile for your device (iOS, macOS, Android), and install it.

### Method B: Homelab (Pi-hole / AdGuard Home)
1. Open your local Pi-hole or AdGuard Home dashboard.
2. Go to **Adlists** or **Blocklists**.
3. Add the raw URL of the `jamf-domains.txt` file from this GitHub repository.
4. Save and update your gravity database.

### blocklists

albert.apple.com
iprofiles.apple.com
mdmenrollment.apple.com
deviceenrollment.apple.com
mesu.apple.com
configuration.apple.com
configuration.ls.apple.com
ocsp2.apple.com
cdn.smoot.apple.com

jamfschool.com
jamfnow.com
jamf.com
jamfcloud.com
mdm-na1.jamfcloud.com
3000619.mdm.jamfschool.com
root.edu.3000619.jamfschool.com
ap-northeast-1.resources.school.jamf.com
leader.edu.3000619.jamfschool.com
member.edu.3000619.jamfschool.com
apne1-jschool-prod240117.alb.internal.jamfcloud.com

This logic is open-source. Feel free to modify, share, or build upon this blocklist. If you include this list in other tools, giving credit is highly appreciated!

## ⚖️ Terms of Service, Privacy Policy, and Liability Disclaimer

### 1. DEFINITIONS AND SCOPE OF AGREEMENT
This document constitutes a binding legal notice governing the use of this repository, its associated configuration files, and any experimental public demonstration network endpoints provided. 
* **"Provider"** refers to Fryvo, including any infrastructure, maintainers, or development entities operating under this project.
* **"The Service"** refers to any public demo DNS endpoints, routing structures, or blocklists hosted or maintained by Fryvo.
* **"The User"** refers to any individual, device, or automated process connecting to, downloading, or applying assets from this project.

### 2. ACKNOWLEDGEMENT OF EXPERIMENTAL RISK (PROOF OF CONCEPT ONLY)
The Service and documentation provided by Fryvo are deployed strictly as an experimental, educational Proof of Concept (PoC). The project exists solely to demonstrate the theoretical mechanics of network-layer domain mitigation against third-party Mobile Device Management (MDM) frameworks. 

* **No Commercial Warranty:** The Service is NOT a commercial software product and is NOT intended, designed, or optimized for daily operational use, production environments, or deployment on primary personal, commercial, or academic hardware.
* **User Assumption of Risk:** By utilizing the public demo server or applying configurations from this repository, the User explicitly acknowledges that they are executing unverified network alterations at their own sole discretion and risk.

### 3. PRIVACY POLICY & DATA HANDLING (PUBLIC DEMO ENDPOINT)
In the event that a User establishes a network connection to the public demonstration endpoint hosted by Fryvo, the User explicitly consents to the following data practices, limitations, and operational realities:

* **Non-Commercialization Pledge:** Fryvo guarantees that it will not sell, lease, publish, trade, or intentionally distribute the User's internet traffic queries, Internet Protocol (IP) addresses, or Domain Name System (DNS) logs to external corporate marketing entities or third-party data brokers.
* **ABSOLUTE EXCLUSION OF SECURITY GUARANTEES:** Because the underlying infrastructure is operated as an independent hobbyist project, **absolute data safety, encryption integrity, and privacy cannot be guaranteed.** The Service may be subject to unexpected security vulnerabilities, network packet sniffing, configuration errors, hosting provider outages, or external malicious interventions entirely beyond the control of Fryvo.
* **Unannounced Modification of Infrastructure:** Fryvo retains the absolute right to alter, modify, reset, or radically transform the architecture, logging practices, data retention limits, and backend protocols of the Service at any given moment **without prior warning, written notification, or disclosure** to the User.
* **Data Transmission Liability:** If the User routes sensitive personal information, credentials, authentication tokens, financial data, or private communications through the Service and experiences a data breach or interception, the User accepts total, undivided liability for that outcome.

### 4. COMPLETE EXCLUSION OF LIABILITY (INDEMNIFICATION)
Under no circumstances shall Fryvo, its developers, or associated entities be held legally or financially liable for any direct, indirect, incidental, consequential, special, or exemplary damages, financial losses, or system errors resulting from the use, misuse, execution, or implementation of this repository, its blocklists, or the Service. This comprehensive exclusion of liability covers, but is not limited to:

* **Hardware Malfunction & Failures:** Device instability, system lockups, boot-loops, loss of local network connectivity, failure to receive essential operating system updates, or errors requiring a factory hardware reset.
* **Institutional Discipline & Compliance Violations:** Any disciplinary actions, academic suspensions, expulsions, employment terminations, or legal actions faced by the User from schools, universities, employers, or network IT administrators for circumventing internal administrative network policies.
* **External Interception:** The monitoring, logging, or tracking of user traffic by local Internet Service Providers (ISPs), network gateways, or malicious third-party actors.

### 5. LEGAL USE AND THIRD-PARTY TRADEMARKS
This project operates with zero affiliation, association, authorization, sponsorship, or endorsement from Jamf Pro, Apple Inc., or any of their subsidiary corporate brands. All product names, logos, and registered trademarks remain the exclusive property of their respective owners. 

The Service and configurations are shared under the prerequisite that the User possesses full legal ownership, administrative authority, and explicit authorization over the specific hardware device they are altering. Circumventing administrative profiles on institutional property that does not belong to the User may violate regional network access laws, institutional codes of conduct, or corporate terms of service. Fryvo does not condone, encourage, or facilitate unauthorized network exploitation.

**BY ENGAGING WITH, DEPLOYING, OR CONNECTING TO ANY ASSET OR SERVICE MAINTAINED BY FRYVO, YOU EXPLICITLY CONFIRM THAT YOU HAVE READ, UNDERSTOOD, AND AGREED TO THESE TERMS, AND INTEND TO HOLD THE PROVIDER COMPLETELY BLAMELESS FOR ANY RESULTING DATA OUTAGES, SYSTEM CRASHES, OR DISCIPLINARY CONSEQUENCES.**