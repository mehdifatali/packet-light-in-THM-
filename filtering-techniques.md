# Wireshark Filtering Techniques

During the Packed Light investigation, I used several Wireshark display filters to narrow down network traffic and identify suspicious activity.

## Filters Used

- `http` – Filtered HTTP traffic.
- `http.request.method == "GET"` – Displayed HTTP GET requests.
- `tcp` – Displayed TCP packets.
- `ip.addr == 192.168.1.141` – Filtered traffic related to the identified client IP.

## Purpose

These filters helped me focus on relevant network packets, investigate HTTP communication, and identify suspicious data transfers.


<img width="954" height="579" alt="image" src="https://github.com/user-attachments/assets/989bd7fe-2e7c-4c39-9fc5-8d2cbce4a7ce" />
# http.request.method == "GET"` – Displayed HTTP GET requests.
 <img width="951" height="572" alt="image" src="https://github.com/user-attachments/assets/302b9e7c-e3d5-4704-bda9-24d6c984787d" />
