# Firewall-Configuration-and-Traffic-Filtering-Windows-
I have done a Firewall Configuration and traffic Filtering. this is my report on it 
# 🔒 Firewall Configuration and Traffic Filtering (Windows)

## 🧩 Objective
To understand how a firewall filters network traffic by configuring rules to block and allow specific ports, and testing their effects on a Windows system.

---

## ⚙️ Steps Performed

### **1. Open Windows Firewall Configuration Tool**
- Go to **Control Panel → System and Security → Windows Defender Firewall**  
  or  
- Open **Command Prompt / PowerShell** as Administrator.

📸 **Screenshot:**  
`[Insert screenshot of Windows Firewall home screen]`

---

### **2. List Current Firewall Rules**
Use the following command to display all existing rules:
```cmd
netsh advfirewall firewall show rule name=all
```

📸 **Screenshot:**  
`[Insert screenshot showing listed firewall rules]`

---

### **3. Add a Rule to Block Inbound Traffic on Port 23 (Telnet)**
Add a new rule to block inbound connections on TCP port 23:
```cmd
netsh advfirewall firewall add rule name="Block Telnet" dir=in action=block protocol=TCP localport=23
```

📸 **Screenshot:**  
`[Insert screenshot showing rule added successfully]`

---

### **4. Test the Rule**
Try to connect to port 23 locally to verify the rule works:
```cmd
telnet localhost 23
```
**Expected Result:** Connection fails or is refused.

📸 **Screenshot:**  
`[Insert screenshot showing connection failed]`

---

### **5. Remove the Test Block Rule**
Once testing is complete, remove the Telnet block rule to restore the original state:
```cmd
netsh advfirewall firewall delete rule name="Block Telnet"
```

📸 **Screenshot:**  
`[Insert screenshot showing rule deleted successfully]`

---

## 🧾 Summary of Commands Used

| Step | Action | Command |
|------|---------|----------|
| 1 | Open Firewall | `control firewall.cpl` *(optional shortcut)* |
| 2 | List Rules | `netsh advfirewall firewall show rule name=all` |
| 3 | Block Port 23 | `netsh advfirewall firewall add rule name="Block Telnet" dir=in action=block protocol=TCP localport=23` |
| 4 | Test Rule | `telnet localhost 23` |
| 5 | Remove Rule | `netsh advfirewall firewall delete rule name="Block Telnet"` |

---

## 🔍 Summary: How a Firewall Filters Traffic
A **firewall** monitors and controls incoming and outgoing network traffic based on defined security rules.  
It acts as a **barrier** between a trusted internal network and untrusted external networks (like the Internet).

### **Key Points:**
- Filters traffic based on **IP address**, **port number**, and **protocol**.  
- **Inbound rules** control traffic entering the system.  
- **Outbound rules** control traffic leaving the system.  
- Blocking or allowing specific ports protects the computer from unauthorized access or unwanted connections.  
- For example, blocking **Telnet (port 23)** prevents unsecured remote access.

---

## 📷 Recommended Screenshots

| Step | Screenshot Description |
|------|------------------------|
| 1 | Windows Firewall home window |
| 2 | Command Prompt showing list of rules |
| 3 | Rule added confirmation |
| 4 | Telnet connection failure message |
| 5 | Rule deleted confirmation |

---

### ✅ Author
**Name:** Karthik  
**Task:** Internship Task – Firewall Configuration (Windows)  
**Platform:** Windows Defender Firewall  
**Date:** October 2025
