
# Jamf DNS Bypass

A simple, lightweight method to block Jamf MDM profiles This method **does not require a PC**, paid tools, or jailbreaking/rooting. 

> ⚠️ **Privacy Notice:** 
i do not recommend using demo DNS profile 
use your own DNS like NextDNS or local tools like Pi-hole.

## How It Works
When a managed device boots up or connects to the internet, it pings specific Apple and Jamf servers to pull down MDM. By using a DNS, we drop those requests before they ever reach the device



## Self Hosted Setup Instructions

### Method A: NextDNS
1. Go to [NextDNS](https://nextdns.io) and create a free account.
2. In your dashboard, navigate to the **Denylist** tab.
3. Copy the domains from the `jamf-domains.txt` file in this repository or blocklist below and paste them in.
4. Go to the **Setup** tab on NextDNS, download the configuration profile for your device (iOS, macOS, Android), and install it.

### Method B: Homelab (Pi-hole / AdGuard Home)
1. Open your local Pi-hole or AdGuard Home dashboard.
2. Go to **Adlists** or **Blocklists**.
3. Add the raw URL of the `jamf-domains.txt` file from this GitHub repository or blocklist below.
4. Save and update your gravity database.

### blocklists
```text
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
```

get an full list form `jamf-domains.txt`

## ⚖️ Liability Disclaimer
### use at your own risk i do not responsible for any outcome 