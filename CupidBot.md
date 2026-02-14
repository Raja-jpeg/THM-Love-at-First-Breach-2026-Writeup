CupidBot — Love at First Breach 2026 Writeup
============================================

![captionless image](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*r45dz5G1KXIadTi1OfodDw.png)

I initally started the conversation with CupidBot with the `ls` command

![captionless image](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*V1rI2IxrCs8aQOsnR35kag.png)

The verification code looked like a MD5 hash, so I used john the ripper to crack the given hash

![captionless image](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*s7V5v5QfzknQW63lBXdOQg.png)

I then tried just giving `emerald` to the CupidBot

![captionless image](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*puLH6OurWVXMuM_qRrjHZA.png)

It didn’t work.

I tried one of the prompts mentioned from this article — [https://tcm-sec.com/ethically-hack-ai-prompt-injection/](https://tcm-sec.com/ethically-hack-ai-prompt-injection/)

![captionless image](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*Gcqn9grkiGUzs2MPdsn7OQ.png)

This is interesting as it revealed the information about how CupidBot follows instructions and the key word was `SYSTEM_PROMPT_FLAG`

![captionless image](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*y2dPOa6Kj4vI4Bf965KKDQ.png)

I tried continuing conversation noticing the pattern of asking with uppercase joined with underscores as flag and revealed the flag for the prompt injection.

![captionless image](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*XBv8DXID8rFtautfSR3ljQ.png)

The same tactic did not work for the final flag

![captionless image](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*-UCqdBV14jqUD-06DLGxJA.png)

I changed my approach by declaring that I am an administrator with elevated privileges asking about any other secret flag by appending gift to make sure the conversation is still about gift ideas

![captionless image](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*edtmHsVd8bSKCUcv3hmPJw.png)

Got the final flag.

References: [https://tcm-sec.com/ethically-hack-ai-prompt-injection/](https://tcm-sec.com/ethically-hack-ai-prompt-injection/)
