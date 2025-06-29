# Internship_Task4
# Task 4 - Setup and Use a Firewall on Windows

## Objective
Configure and test Windows Firewall rules to block and allow specific network traffic. This helps in understanding how firewalls filter traffic and enhance system security.

---

## System Used
- **OS:** Windows 10 / 11
- **Tool:** Windows Defender Firewall with Advanced Security

---

## Steps Followed

### Step 1: Open Windows Firewall Settings
- Press `Windows + R`, type `wf.msc`, and hit Enter
- This opens **Windows Defender Firewall with Advanced Security**
![Screenshot 2025-06-29 180225](https://github.com/user-attachments/assets/630a896b-c313-4644-9565-b5b855044325)

---

### Step 2: Block Inbound Traffic on Port 23 (Telnet)
1. Click **Inbound Rules** → **New Rule**
2. Select **Port**, click **Next**
   ![Screenshot 2025-06-29 180448](https://github.com/user-attachments/assets/35f21efa-3f29-4fad-b415-af90b8ad1045)

4. Choose **TCP**, enter port `23`, click **Next**
5. Choose **Block the connection**, click **Next**
6. Select all profiles (Domain, Private, Public), click **Next**
  ![Screenshot 2025-06-29 181106](https://github.com/user-attachments/assets/86df04ca-37cb-4a51-9ed0-efaeedfb155b)


8. Name the rule **"Block Telnet Port 23"** → click **Finish**

---

### Step 3: (Optional) Allow SSH (Port 22)
If needed:
1. Create a new rule just like above
2. Enter port **22**
3. Select **Allow the connection**
4. Name it **"Allow SSH Port 22"**

---

## Testing the Rule

### Step 4: Enable Telnet (for Testing)
1. Open **Command Prompt as Administrator**
2. Run:
   ```cmd
   dism /online /Enable-Feature /FeatureName:TelnetClient
   ![Screenshot 2025-06-29 181621](https://github.com/user-attachments/assets/09b00091-2b98-453a-80ba-f4a774074705)


### Step 5: Test Port 23 Block
Run this in Command Prompt:
```cmd
telnet localhost 23
```
If firewall is correctly blocking the port:
- Connection fails or times out
- No Telnet banner or prompt appears
![Screenshot 2025-06-29 182036](https://github.com/user-attachments/assets/cdbe6d4b-b68b-4376-b2d9-8af22280f709)

## **Outcome** 
Basic firewall management skills and understanding of network traffic filtering.
