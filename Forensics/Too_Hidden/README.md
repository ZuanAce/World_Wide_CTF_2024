# Too Hidden ✅

## Challenge Description
> ![image](https://github.com/user-attachments/assets/8ab9c48e-d3ea-4171-b248-e439cd145eaf)

----

## Challenge Overview
Opening the provided `chall.pcapng` in Wireshark, I noticed a significant amount of ICMP ping requests. Upon further inspection, the last two bytes in the data section of the packets appeared repetitive but suspiciously different.  

![image](https://github.com/user-attachments/assets/43558449-f6cd-4883-afb3-c2e75cdd5bf3)

 ----

## Solution Approach
1. **Extract Data:** To extract the suspicious data, I used the following `tshark` command:
   ```bash
   tshark -r chall.pcapng -Y "icmp.type == 8" -T fields -e data > bytes.txt
   ```
   This extracted the data payload of all ICMP ping request packets (icmp.type == 8) into a file called bytes.txt.

2. **Convert Hex Data to ASCII:** Next, I created a Python script to convert the extracted hexadecimal data into ASCII characters. Here's the script:
   ```python
   # Read the extracted hex data
   with open("bytes.txt", "r") as f:
       hex_lines = f.readlines()
   
   # Convert hex to ASCII
   with open("ascii_output.txt", "w") as out:
       for line in hex_lines:
           if line.strip():  # Ignore empty lines
               # Remove colons if present and convert to ASCII
               ascii_text = bytes.fromhex(line.strip().replace(":", "")).decode('utf-8', errors='ignore')
               out.write(ascii_text + "\n")
   ```
   This generates an ascii_output.txt file containing the ASCII representation of the data.

3. **Analyze the ASCII Data:** Copying the content of ascii_output.txt into CyberChef, I noticed the data resembled Morse code. Using the `From Decimal` operation with `delimiter CRLF`, the Morse code was revealed.
   ```.-- .-- ..-.  .... --- .-.. -.-- ..--.- ... .... . . . . - ..--.- -.-- --- ..- ..--.- -.-. .- -. ..--.- ..-. .. -. -.. ..--.- -- . ..--.- ..--.. ..--.. ..--.. ..--.. ..--.. ..--.. ..--.. ..--.. ..--.. ..--.. ```
   
   ![image](https://github.com/user-attachments/assets/68db5249-b3a0-4570-999a-ab04bb8c01be)

4. **Decode the Morse Code:** Using CyberChef's Magic feature, I decoded the Morse code into a readable message. The flag was revealed as: `WWFHOLY_SHEEEET_YOU_CAN_FIND_ME_??????????`. Adding the curly brackets, the final flag is:
   `WWF{HOLY_SHEEEET_YOU_CAN_FIND_ME_??????????}`.

   ![image](https://github.com/user-attachments/assets/9f7e453c-4be4-444a-be24-dd0d10d89771)

----
   
## Flag: 
WWF{HOLY_SHEEEET_YOU_CAN_FIND_ME_??????????}

   





