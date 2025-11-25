# **CyberArk Privileged Account Lifecycle Management**

A practical walkthrough of end-to-end CyberArk Privileged Access Management (PAM) workflows — from onboarding privileged accounts to applying platform policies, rotating credentials, and launching monitored PSM sessions.

<div align="center">
  <img width="600" height="600" alt="image" src="https://github.com/user-attachments/assets/c72d5b37-7967-4962-99ae-6cfdc75c0851" />
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
![Screenshot](SS_01_PVWA_Dashboard.png)

---

## **Step 2 — Create Privileged Accounts in AD**

In the Domain Controller:

1. Open **Active Directory Users and Computers**  
2. Create two demo privileged accounts:  
   - `LocalAdmin_Server1`  
   - `Service_Account_SQL`

**Privileged AD accounts created for onboarding 👥**  
![Screenshot](SS_02_AD_NewUsers.png)

---

## **Step 3 — Create a Safe**

Navigate to **PVWA → Administration → Safes → Add Safe**:

- **Name:** `IT_Admins_Safe`
- **Owner:** Yourself  
- Keep default retention settings

**Safe created to store privileged credentials securely 🔐**  
![Screenshot](SS_03_Safe_Created.png)

---

## **Step 4 — Onboard Privileged Accounts**

Go to **PVWA → Safes → IT_Admins_Safe → Add Account**

For each account:

- **Platform:** Windows Local / Windows Server  
- **Address:** `10.0.0.3`  
- **User:** `LocalAdmin_Server1` / `Service_Account_SQL`  
- **Secret:** Temporary password  

**Privileged account added and secured in the Vault ✅**  
![Screenshot](SS_04_Account_Added.png)

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

A complete demonstration of **CyberArk Privileged Access Lifecycle Management** from creation → onboarding → securing → rotating → monitoring.  
