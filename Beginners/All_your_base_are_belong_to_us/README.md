# All your base are belong to us ✅

## Challenge Description
> ![image](https://github.com/user-attachments/assets/940c155c-125d-4b4a-aa22-917c8df6907f)

----

## Challenge Overview
In this challenge, we were provided with a string that appeared to be encoded in a custom base, and our task was to decode it to reveal a flag. The string was:

`MkpIbmdFcWs4MzVjR3BHRXFVVnZtZWJUQWtSTlNNamE1dGZYQTdwR25ac203SnJQV2FyTUdHQnA3Uk1XZDNZVFlTNTJjemVya1BCN0dBY2NBNkN4U1VBS29TalVBOU1tR1EyYUF0UVlHZTFYOXp1TThWS2o1OHdKRFJaVXhzTGRaZUpaTGV6NUFWc2JHdm5CbTdjV28yNTRyWGpzQURYdEhkSmJmWmtGREVEQWZWeEhFeDNYanNNODZMZVo2cnM2NExGbU5QeG1mUXBqQ3BoY3pCczlRa3kySnFZb1JzSnFtUnk0cW02WFgyOU50N1g2Vg`

 ----

## Solution Approach
1. **Use CyberChef:** I pasted the string into CyberChef and used the “Magic” button to try out different decodings. After several attempts, I eventually got a string containing Chinese characters: `𔕷𠅦𖥣桢顲桨鑦敤𓅥𓉮鵟𔐴鐳ꌴ鑬鵴鐳𐘴𔕳𓀳鑳𔔴敧栴鬲ᕽ`

   ![image](https://github.com/user-attachments/assets/e92d980c-b066-41a6-a2a4-cc7cb3cc21d1)

2. **Use Base 65536 Decoding:** In the challenge description, a hint was given indicating the use of base $2^16$. I found an (online tool)[https://www.better-converter.com/Encoders-Decoders/Base65536-Decode] for decoding Base 65536 and input the Chinese characters. When decoded, the result was the flag:

   ![image](https://github.com/user-attachments/assets/96b10555-1978-4ee3-bd81-d188b985f406)

----
   
## Flag: 
wwf{cyb3rch3f_d0esnt_h4v3_4ll_th3_4nsw3rs_4wg0432f}


   




