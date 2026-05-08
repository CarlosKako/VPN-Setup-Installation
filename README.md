

<h1>ProtonVPN Setup, Installation & Verification on Azure VM</h1>

This project demonstrates the full workflow of deploying and verifying ProtonVPN on a Windows 10 virtual machine hosted in Microsoft Azure, accessed via Remote Desktop Protocol (RDP).

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines / Compute)
- Remote Desktop Protocol (RDP)
- ProtonVPN (Free Tier)

<h2>Operating System Used</h2>

- Windows 10 Pro (21H2)

<h2>High-Level Steps</h2>

1. Create a Windows 10 VM in Microsoft Azure
2. Connect to the VM via Remote Desktop
3. Check baseline public IP address (before VPN)
4. Create a ProtonVPN account and install the client
5. Connect to a ProtonVPN server
6. Verify IP address changed (after VPN)

---

<h2>Step 1 — Create a Windows 10 Virtual Machine in Azure</h2>

<p>
<!-- SCREENSHOT: Azure portal showing VM creation (resource group, region, Windows 10 image selected) -->
<img width="1610" height="654" alt="image" src="https://github.com/user-attachments/assets/62e81ded-0de3-4334-abfc-823b777239d5" />
</p>
<p>
In the Azure portal, I created a new Virtual Machine using the Windows 10 Pro (21H2) image. I configured the resource group, region, VM size, and set up an admin username and password that would be used for RDP access.
</p>
<br />

---

<h2>Step 2 — Connect to the VM via Remote Desktop (RDP)</h2>

<p>
<!-- SCREENSHOT: RDP login screen or Remote Desktop Connection window with the VM's public IP -->
<img width="1918" height="1038" alt="image" src="https://github.com/user-attachments/assets/aaed0eb0-d0d1-4f33-915a-098daf5bc793" />
</p>
<p>
Once the VM was running, I copied its public IP address from the Azure portal and connected using Windows Remote Desktop (mstsc). I logged in with the admin credentials set during VM creation, gaining full access to the virtual desktop.
</p>
<br />

---

<h2>Step 3 — Check Baseline Public IP Address (Before VPN)</h2>

<p>
<!-- SCREENSHOT: Browser inside the VM showing whatismyipaddress.com or whatismyip.com — NO VPN connected yet -->
<img width="1203" height="482" alt="image" src="https://github.com/user-attachments/assets/e0227eab-59d9-42af-aa8c-ccf0cf4ae830" />
</p>
<p>
Inside the VM, I opened a browser and visited <strong>whatismyipaddress.com</strong> to record the VM's current public IP address and geographic location. This baseline will be compared after connecting to the VPN to confirm the traffic is being rerouted.
</p>
<br />

---

<h2>Step 4 — Create a ProtonVPN Account and Install the Client</h2>

<p>
<!-- SCREENSHOT: ProtonVPN website account creation or download page -->
<img width="1610" height="654" alt="image" src="https://github.com/user-attachments/assets/62e81ded-0de3-4334-abfc-823b777239d5" />
</p>
<p>
I navigated to <strong>protonvpn.com</strong> and created a free account. After confirming the email, I downloaded the ProtonVPN Windows installer directly onto the VM.
</p>
<br />

<p>
<!-- SCREENSHOT: ProtonVPN installer running on the VM -->
<img width="597" height="467" alt="image" src="https://github.com/user-attachments/assets/a6b88cc1-94d2-4fbc-9e04-2e401ec177cb" />
</p>
<p>
I ran the installer and followed the on-screen prompts to complete the installation. Once installed, I launched the ProtonVPN client and logged in using the account credentials created in the previous step.
</p>
<br />

---

<h2>Step 5 — Connect to a ProtonVPN Server</h2>

<p>
<!-- SCREENSHOT: ProtonVPN client showing server selection and active/connected status -->
<img width="1001" height="655" alt="image" src="https://github.com/user-attachments/assets/319e218a-bd91-4499-9811-e9ce85b83315" />
</p>
<p>
Inside the ProtonVPN client, I selected a server in a different country/region and clicked Connect. The client confirmed an active connection, displaying the assigned VPN server IP, connection status, and encrypted tunnel indicator.
</p>
<br />

---

<h2>Step 6 — Verify IP Address Changed (After VPN)</h2>

<p>
<!-- SCREENSHOT: Same browser/site (whatismyipaddress.com) now showing a NEW IP and different location -->
<img width="1203" height="482" alt="image" src="https://github.com/user-attachments/assets/e0227eab-59d9-42af-aa8c-ccf0cf4ae830" />
</p>
<p>
With the VPN active, I revisited <strong>whatismyipaddress.com</strong>. The public IP address and geographic location had changed to match the ProtonVPN server I connected to, confirming that all internet traffic from the VM was now being routed securely through the VPN tunnel.
</p>

| | Before VPN | After VPN |
|---|---|---|
| **IP Address** | *(Azure VM public IP)* | *(ProtonVPN server IP)* |
| **Location** | *(Azure datacenter region)* | *(VPN server country)* |

<br />

---

<h2>Conclusion</h2>

This project demonstrated a complete VPN deployment workflow in a cloud environment: provisioning an Azure VM, connecting via RDP, installing and configuring ProtonVPN, and verifying the VPN's effectiveness through a before-and-after IP address comparison. This setup mirrors real-world IT scenarios where remote machines require secure, encrypted tunneling for privacy and access control.
