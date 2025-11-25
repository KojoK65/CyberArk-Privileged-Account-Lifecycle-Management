# **🔐 CyberArk Privileged Account Lifecycle Management** 

A practical walkthrough of end-to-end CyberArk Privileged Access Management (PAM) workflows — from onboarding privileged accounts to applying platform policies, rotating credentials, and launching monitored PSM sessions.

<div align="center">
  <img src="https://github.com/user-attachments/assets/c72d5b37-7967-4962-99ae-6cfdc75c0851" alt="Overview Image" style="width:50%; height:auto;" />
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
  <img src="https://github.com/user-attachments/assets/c0a59876-e4b6-4cb5-a09d-425a1f9893ed" alt="PVWA Dashboard" style="width:80%; height:auto;" />
</div>

---

## **Step 2 — Created Privileged Accounts**

On the VM:

1. Create the privileged account:  
   - `LocalAdmin_Server1`
2. Add the account to the **Administrators** group

**Privileged account created and granted admin rights 👥**  
<div align="center">
  <img src="https://github.com/user-attachments/assets/366b106c-6c8a-41cd-82ed-3617b7de5a7d" alt="Creating LocalAdmin_Server1" style="width:80%; height:auto;" />
  <img src="https://github.com/user-attachments/assets/f3b1fb04-17ad-4caf-a93d-30c188c26672" alt="Adding LocalAdmin_Server1 to Administrators" style="width:80%; height:auto;" />
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

## **Step 4 — Configure Platform Policies**

Cloned the Windows platform in PVWA and configured key settings:

- Password complexity  
- Password rotation  
- Reconcile account settings  

**Platform policy configured for password lifecycle automation ⚙️**  

<div align="center">
  <img src="https://github.com/user-attachments/assets/9be9118f-bf43-47d4-98ba-7f64a9e1a812" alt="Platform Policy Configured" style="width:80%; height:auto;" />
</div>

---

## **Step 5 — Assign Safe Permissions**

Prepared the Safe by configuring role-based access controls for members:

- List Accounts  
- Retrieve Accounts  
- Use Accounts  

**Safe members before adding the demo users.**

<div align="center">
  <img src="https://github.com/user-attachments/assets/8f2faa43-d8a2-44c6-a7da-f4e4db1a3cfa" alt="Safe Members Before Demo Users" style="width:80%; height:auto;" />
</div>

---

## **Step 6 — Onboard Privileged Accounts**

Go to **PVWA → Accounts View → Add Account** to add the users:

- **Platform:** WindowsLocal_Admin  
- **Address:** `10.0.0.3`  
- **User:** `LocalAdmin_Server1` / `Service_Account_SQL`  

**Privileged accounts added and secured in the Vault ✅**  

<div align="center">
  <img src="https://github.com/user-attachments/assets/33ba173a-a0da-4d44-88f8-05c97276d367" alt="Onboard Account 1" style="width:80%; height:auto;" />
  <img src="https://github.com/user-attachments/assets/8c19888f-7189-4c68-a5b2-2372e8bdd57b" alt="Onboard Account 2" style="width:80%; height:auto;" />
</div>

---

## **Step 7 — Trigger CPM Verify/Change**

Validated and rotated the password:

**PVWA → Accounts View → LocalAdmin_Server1 → CPM Actions → Verify / Change**

**Password verified and reconciled successfully 🔁**  

<div align="center">
  <img src="https://github.com/user-attachments/assets/ccc553fa-d89d-40f8-ad3c-a580c921416f" alt="CPM Verify/Change Success" style="width:80%; height:auto;" />
</div>

---

## **Step 8 — Launch a PSM Session**

Open a PSM-brokered secure session:

**PVWA → Accounts → LocalAdmin_Server1 → Connect**

During a PSM session:

- Users never see the password  
- Session is fully audited & recorded  
- Keystrokes and actions are monitored  

**PSM privileged session initiated and monitored 🎥**  

<div align="center">
  <img src="https://github.com/user-attachments/assets/a859d8ae-af4a-4954-be2e-fcc7f198dcba" alt="Enter PSM Reason" style="width:80%; height:auto;" />
  <img src="https://github.com/user-attachments/assets/7396d53e-b03e-47f7-832e-eaa115a5cd2a" alt="PSM Session Successful Launch" style="width:80%; height:auto;" />
</div>

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
