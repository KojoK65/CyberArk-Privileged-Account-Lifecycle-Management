# **🔐 CyberArk Privileged Account Lifecycle Management**

A practical walkthrough of end-to-end CyberArk Privileged Access Management (PAM) workflows — from onboarding privileged accounts to applying platform policies, rotating credentials, and launching monitored PSM sessions.

<div align="center">
  <img width="420" height="420" alt="image" src="https://github.com/user-attachments/assets/c72d5b37-7967-4962-99ae-6cfdc75c0851" />
</div>

---

## 🎯 **Objective**


Demonstrate core CyberArk PAS lifecycle operations, including:

- Onboarding AD & service accounts  
- Creating and managing Safes  
- Applying platform policies  
- Automating password rotation (CPM)  
- Launching PSM-brokered privileged sessions  
- Reviewing audit logs & session recordings  

---

## **Step 1 — Access PVWA**

Log in to the Password Vault Web Access (PVWA) portal:

`https://<PVWA_HOST>/PasswordVault/`

**PVWA Dashboard — central hub for PAM operations 🧭**  

<div align="center">
  <img src="https://github.com/user-attachments/assets/c0a59876-e4b6-4cb5-a09d-425a1f9893ed" alt="PVWA-CPM-PSM-2025-11-10-14-59-07" style="width:75%; height:auto;" />
</div>

---


## **Step 2 — Created Privileged Accounts**

On the VM:

1. Create the privileged account:  
   - `LocalAdmin_Server1`
2. Add the account to the **Administrators** group

**Privileged account created and granted admin rights 👥**  
<div align="center">
  <img src="https://github.com/user-attachments/assets/366b106c-6c8a-41cd-82ed-3617b7de5a7d" alt="Creating LocalAdmin_Server1" style="width:75%; height:auto;" />
  <img src="https://github.com/user-attachments/assets/f3b1fb04-17ad-4caf-a93d-30c188c26672" alt="Adding LocalAdmin_Server1 to Administrators" style="width:75%; height:auto;" />
</div>

---

## **Step 3 — Created a Safe**

1. Created a new Safe named **IT_Admins_Safe**  
2. Added myself as the owner  
3. Kept default retention settings

**Safe created to securely hold privileged accounts 🔐**  
<div align="center">
  <img src="https://github.com/user-attachments/assets/5aae5f77-096f-40ea-99b6-528ddeadff90" alt="IT_Admins_Safe Created" style="width:80%; height:auto;" />
</div>

---


## **Step 4 — Onboard Privileged Accounts**

Go to **PVWA → Accounts View → Add Account**

For each account:

- **Platform:** WindowsLocal_Admin  
- **Address:** `10.0.0.3`  
- **User:** `LocalAdmin_Server1` / `Service_Account_SQL`  
- **Secret:** Temporary password  

**Privileged account added and secured in the Vault ✅**  
<img width="1920" height="1080" alt="PVWA-CPM-PSM-2025-11-10-15-11-24" src="https://github.com/user-attachments/assets/33ba173a-a0da-4d44-88f8-05c97276d367" />
<img width="1920" height="1080" alt="PVWA-CPM-PSM-2025-11-10-16-17-20" src="https://github.com/user-attachments/assets/a1aa1a46-87a4-4602-af54-21dbe98fad41" />

---

## **Step 5 — Assign Safe Permissions**

Navigate to **PVWA → Safes → IT_Admins_Safe → Members**

Assign appropriate permissions:

- List Accounts  
- Retrieve Accounts  
- Use Accounts  
- Manage Safe (optional, admin-level)

**RBAC permissions applied to Safe members 👥🔒**  
![Screenshot](SS_05_Safe_Members.png)

---

## **Step 6 — Configure Platform Policies**

Go to **PVWA → Administration → Platform Management**

Best practice: **Clone the Windows platform**, then configure:

- Password complexity  
- Password rotation (e.g., every 7 days)  
- Reconcile account settings  
- Privileged commands (optional)  

**Platform policy configured for password lifecycle automation ⚙️**  
![Screenshot](SS_06_Platform_Config.png)

---

## **Step 7 — Trigger CPM Verify/Change**

To initiate password rotation:

**PVWA → Safes → Accounts → LocalAdmin_Server1 → CPM Actions → Verify / Change**

Monitor real-time CPM status in:

**Monitoring → CPM Jobs**

**CPM verification and rotation successfully executed 🔁**  
![Screenshot](SS_07_CPM_Reconcile_Success.png)

---

## **Step 8 — Launch a PSM Session**

Open a PSM-brokered secure session:

**PVWA → Accounts → LocalAdmin_Server1 → Connect**

During a PSM session:

- Users never see the password  
- Session is fully audited & recorded  
- Keystrokes and actions are monitored  

**PSM privileged session initiated and monitored 🎥**  
![Screenshot](SS_08_PSM_Connect.png)

---

## **Final PSM Recording View**

**Active PSM session with recording enabled ⭐**  
![Screenshot](SS_09_PSM_Session_Recording.png)

---

# 🎯 **Final Outcome**

By the end of this hands-on lifecycle demonstration, I successfully:

🔐 Onboarded privileged AD & service accounts into CyberArk  
🗄️ Created and secured a dedicated Safe for credential storage  
👥 Applied RBAC-based Safe permissions for controlled access  
⚙️ Configured platform policies for automated password rotation  
🔁 Executed CPM Verify/Change workflows for credential lifecycle  
🖥️ Launched monitored PSM sessions without ever exposing passwords  
🎥 Reviewed audit logs and session recordings for compliance  
