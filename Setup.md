# Setting Up a VoIP Spoofing Environment

This section outlines how malicious actors could set up VoIP spoofing systems to deploy P1 bots. Our research setup uses the SIP provider [voizhen.com](https://voizhen.com) for easy experimentation.

## Step 1: Install Asterisk or FreePBX

- Deploy Asterisk on a Linux VPS (Ubuntu or CentOS preferred)  
- Alternatively, use a FreePBX VM image for easier GUI management  

## Step 2: Configure SIP Trunk

- Register your PBX with the SIP provider at voizhen.com  
- Use SIP credentials assigned from voizhen’s portal  
- Define outbound routes with caller ID manipulation rules  

Example snippet (sip.conf):
[voizhen]
type=peer
host=voizhen.com
username=yourusername
secret=yourpassword
fromuser=yourusername
fromdomain=voizhen.com
insecure=invite,port
qualify=yes


## Step 3: Set Caller ID Spoofing Rules

- Customize outbound caller IDs using Asterisk dial plan  
- Rotate caller IDs dynamically to evade detection  

## Step 4: Deploy Automation Scripts (P1 Bots)

- Integrate your call bot scripts with Asterisk AMI or ARI interfaces  
- Schedule mass call campaigns with spoofed caller IDs via the call feature on the SIP provider.  

## Step 5: Monitor and Analyze Calls

- Collect call logs  
- Use the research tools described in Tools.md 

---

## Ethical Considerations

This setup is intended for cybersecurity research only. Deploying spoofed calls without consent is illegal in most jurisdictions.


