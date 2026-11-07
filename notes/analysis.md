# Initial Step

First, I downloaded the task file provided in the TryHackMe Packed Light room for further analysis.

## 2. Opening the PCAP File

After downloading the task file, I opened it using Wireshark to inspect the captured network traffic.

I started analyzing the packets to identify suspicious communication and understand how the data was transmitted.

## 3. Traffic Analysis and Anomaly Detection

I used different Wireshark display filters to investigate the captured network traffic.

By filtering and examining different types of packets, I identified suspicious traffic patterns and potential anomalies that required further investigation.

<img width="1081" height="159" alt="image" src="https://github.com/user-attachments/assets/baa67538-7418-45e8-8672-dfe4bfc2180b" />

## 4. HTTP Stream Analysis

I followed the HTTP stream in Wireshark to inspect the communication between the client and the server.

By examining the HTTP requests and responses, I discovered a suspicious Python script (`updates.py`).

I analyzed the script's content and understood its logic, including how it captures keyboard input and processes the collected data.
<img width="753" height="774" alt="image" src="https://github.com/user-attachments/assets/538e451c-ac92-4443-aea7-f15c4b7b9ce3" />

And this working, like a "Key-Logger" this code sent every your keyboard actions to "C2-SERVER"   

The script uses the XOR encryption algorithm to encrypt the captured keyboard data. 
It also applies Base64 encoding to transform the encrypted data into a text-based format before transmission.

## 5. Extracting Encrypted Cookies

I examined the HTTP GET requests in Wireshark and inspected the cookies sent with each request.

I extracted the encrypted cookie values from the requests and collected them in a separate text file for further analysis and decryption.

<img width="958" height="1031" alt="image" src="https://github.com/user-attachments/assets/3ca867c8-5fa3-46c7-8a3a-5164965928a1" />

## Then, I combined all the extracted values into a single text file, placing them one after another in the correct order to prepare for decryption.

```text
HA==,AA=,BQ==,Mw==,Hg==,ew==,Og==,fA==,Fw==,eQ==,Ow==,Fw==,Pw==,fA==,PA==,Kw==,IA==,eQ==,Jg==,Lw==,Fw==,eA==,Pg==,LQ==,Gg==,Fw==,MQ==,eA==,PQ==,NQ==
```
## 6. Decrypting Data with CyberChef

After collecting and combining all the encrypted cookie values, I moved to CyberChef for further analysis.

I used the following operations in the correct order:

1. **From Base64** – decoded the Base64-encoded data.
2. **XOR** – decrypted the data using the encryption key.
3. **Decode Text (UTF-8)** – converted the result into readable text.

This process helped me recover the original keyboard input captured by the keylogger.

<img width="1528" height="701" alt="image" src="https://github.com/user-attachments/assets/fa2939ee-ae40-4e0a-bf11-298689d011d8" />

