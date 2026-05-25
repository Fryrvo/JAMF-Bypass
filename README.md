
# Jamf DNS Bypass

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
3. Copy the domains from the `/jamf-domains.txt` file in this repository and paste them in.
4. Go to the **Setup** tab on NextDNS, download the configuration profile for your device (iOS, macOS, Android), and install it.

### Method B: Homelab (Pi-hole / AdGuard Home)
1. Open your local Pi-hole or AdGuard Home dashboard.
2. Go to **Adlists** or **Blocklists**.
3. Add the raw URL of the `/jamf-domains.txt` file from this GitHub repository.
4. Save and update your gravity database.

### Demo versions 
### 📥 Download & Deployment Agreement

demo version make and hosted on NEXT DNS 
you can get demo version on project link 



# blocklists

* albert.apple.com
* iprofiles.apple.com
* mdmenrollment.apple.com
* deviceenrollment.apple.com
* mesu.apple.com
* configuration.apple.com
* configuration.ls.apple.com
* ocsp2.apple.com
* cdn.smoot.apple.com

* jamfschool.com
* jamfnow.com
* jamf.com
* jamfcloud.com
* mdm-na1.jamfcloud.com
* 3000619.mdm.jamfschool.com
* root.edu.3000619.jamfschool.com
* ap-northeast-1.resources.school.jamf.com
* leader.edu.3000619.jamfschool.com
* member.edu.3000619.jamfschool.com
* apne1-jschool-prod240117.alb.internal.jamfcloud.com

it highly recommended to get an list form `/jamf-domains.txt`
Feel free to modify, share, or build upon this blocklist. 
If you include this list in other tools, giving credit is highly appreciated!(but it not required)




## ⚖️ Liability Disclaimer

* **No Commercial Warranty:** The Service is NOT a commercial software product and is NOT intended, designed, or optimized for daily operational use, production environments, or deployment on primary personal, commercial, or academic hardware.
* 
* **User Assumption of Risk:** By utilizing the public demo server or applying configurations from this repository, the User explicitly acknowledges that they are executing unverified network alterations at their own sole discretion and risk.

### COMPLETE EXCLUSION OF LIABILITY (INDEMNIFICATION)
Under no circumstances shall Fryvo, its developers, or associated entities be held legally or financially liable for any direct, indirect, incidental, consequential, special, or exemplary damages, financial losses, or system errors resulting from the use, misuse, execution, or implementation of this repository, its blocklists, or the Service. This comprehensive exclusion of liability covers, but is not limited to:

* **Hardware Malfunction & Failures:** Device instability, system lockups, boot-loops, loss of local network connectivity, failure to receive essential operating system updates, or errors requiring a factory hardware reset.
* **Institutional Discipline & Compliance Violations:** Any disciplinary actions, academic suspensions, expulsions, employment terminations, or legal actions faced by the User from schools, universities, employers, or network IT administrators for circumventing internal administrative network policies.
