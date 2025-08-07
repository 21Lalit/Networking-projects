# 📧 Email Configuration in Cisco Packet Tracer

This guide walks you through configuring an Email Server and Email Client communication using SMTP and POP3 protocols in Cisco Packet Tracer.

---

## 🖥️ Email Server Configuration

1. **Open the Server**
2. Navigate to `Services` > `EMAIL`
3. Enable both:

   * ✅ SMTP Service
   * ✅ POP3 Service
4. Set the **Domain Name** (e.g., `gmail.com`)
5. Under **User Setup**, create users:

   * `user1`, `user2`, `user3` with password `12312345`
  
![Email-Server-Configuration](https://github.com/21Lalit/Networking-projects/blob/main/Email-Configuration/Email-Server-Configuration.png)

---

## 💻 Email Client Configuration

1. Open the PC (e.g., PC3)

2. Go to `Desktop` > `Email`

3. Fill in the fields:

   * **Your Name**: `himanshu`
   * **Email Address**: `user2@gmail.com`
   * **Incoming Mail Server**: `192.168.1.4`
   * **Outgoing Mail Server**: `192.168.1.4`
   * **Username**: `user2`
   * **Password**: `12312345`
  
![Email-Client-Account-Setup](https://github.com/21Lalit/Networking-projects/blob/main/Email-Configuration/Email-Client-Account-Setup.png)

4. Click **Save**

---

## 📥 Sending & Receiving Emails

1. Navigate to `Desktop` > `Email`
2. Use options:

   * `Compose` → Create a new email
   * `Send/Receive` → Sync with the mail server

### ✅ Example:

* **From**: `user1@gmail.com`
* **To**: `user2@gmail.com`
* **Subject**: `Hi`
* **Body**: `Hi there`

Once sent, PC3 (configured for user2) will receive the message successfully from the POP3 server (`192.168.1.4`).

![Mail-Box](https://github.com/21Lalit/Networking-projects/blob/main/Email-Configuration/Mail-Box.png)

> ✅ **Note**: Ensure proper IP connectivity between server and PC (use `ping` to verify).

---

## 🧪 Troubleshooting

* Make sure SMTP & POP3 are turned ON
* Ensure correct username/password
* Verify IP addressing
* Server and client must be in the same subnet or properly routed

---

🎉 You now have a working Email setup in Cisco Packet Tracer!
