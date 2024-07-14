---
title: Self Hosting
parent:
  - "[[Guide]]"
aliases: 
tags:
---
### Meeting Questions
**Security**
- How can I prevent bad actors from seeing my IP address?
- My router doesn't have many firewall settings. Should I invest in a firewall service like Firewalla?
- If I only have low-risk ports open, like 443 for https, is there any way for bad actors to gain entry to my server or home router?
- What will Cloudflare protect me from? Is it enough?
**Routing**
- How can I use proxies like Cloudflare but still enable TCP connections?
- How can I set subdomains to map to specific ports? For example, play.andrewrs.us connects on port 25565 without users having to specify the port number.
- Is my setup optimal?

### Current Structure
**Domain**
- Registered with namecheap
- Routed through Cloudflare nameservers
**DNS**
- CNAME: www.andrewrs.us -> DynamicDNS
- CNAME: play.andrewrs.us -> www.andrewrs.us
**Router**
- Server Address Reserved (10.0.0.36)
- Port Forward: 443 -> 10.0.0.36:443
- Port Forward: 25565 -> 10.0.0.36:25565
**Server Machine**
- Ufw Allow 25565
- Ufw Allow 443
- Ufw Allow 22
	**Docker**
	- Https Using Nginx -p 443:443
	- Minecraft -p 25565:25565