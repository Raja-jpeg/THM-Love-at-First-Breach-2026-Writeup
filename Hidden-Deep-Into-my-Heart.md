Hidden Deep Into my Heart — Love at First Breach 2026
=====================================================

![captionless image](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*-rM_L4Dq7SboQGTgUupjeg.png)

**Challenge:** Cupid’s Vault was designed to protect secrets meant to stay hidden forever. Unfortunately, Cupid underestimated how determined attackers can be.

Intelligence indicates that Cupid may have unintentionally left vulnerabilities in the system. With the holiday deadline approaching, you’ve been tasked with uncovering what’s hidden inside the vault before it’s too late.

You can find the web application here: `[http://T](http://10.65.173.220:5000)ARGET:PORT`

First, I started with nmap scan

![captionless image](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*sCKHsnhiOgMPUkkSlOHxuQ.png)

Nmap scan revealed an interesting endpoint

![captionless image](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*9rgRgF6QwqnIEtc403EUGg.png)

/robots.txt revealed a interesting note: `cupid_arrow_2026!!!`

![captionless image](https://miro.medium.com/v2/resize:fit:916/format:webp/1*UpLwsBvzFl2mvjsvV_q-Lg.png)

then, I bruteforced directories with ffuf

```
ffuf -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -u http://TARGET:PORT/cupids_secret_vault/FUZZ -nc 200, 301, 302 -H "User-Agent: Mozilla/5.0"
```
![captionless image](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*nU85qkQrxRvUVjWHemN2_g.png)

http://TARGET:PORT/cupids_secret_vault/administrator revealed a login page

![captionless image](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*VDHmGRvKvU_z51y76cMN3w.png)

I initially tried brute-forcing username and password with hydra but noticed that it is taking longer than expected so stepped back I tried with the obvious usernames and password with one of them being “`admin`” and “`cupid_arrow_2026!!!`” respectively.

Got the flag!

![captionless image](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*P_UoaiiTh0TUDNo0K9YXqQ.png)
