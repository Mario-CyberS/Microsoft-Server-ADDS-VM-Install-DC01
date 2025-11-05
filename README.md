# Microsoft Server ADDS VM Install — DC01  
This project documents how to deploy **Windows Server 2025** in VMware Workstation 17 Pro and prepare the VM for promotion to an Active Directory Domain Services (AD DS) Domain Controller (DC01). It covers ISO acquisition, VMware VM setup, ISO attachment, and installer configuration for the **Desktop Experience** environment.

---

## 🎯 Objective  
To create a stable, GUI-based Windows Server 2025 virtual machine configured as `DC01`, ready for AD DS role promotion and IAM lab testing.

---

## 🔍 Why Deploy Server 2025 in Workstation?  
This method provides:  
- A realistic, local Active Directory lab environment  
- Full GUI management through **Desktop Experience**  
- Isolated NAT or host-only networking for secure experiments  
- Snapshot support for rollback before risky configuration changes  

---

## 📚 Skills Learned  
- Downloading and verifying Microsoft evaluation ISOs  
- Creating a lab VM in VMware Workstation (Advanced setup)  
- Selecting hardware profiles for server performance and stability  
- Installing the correct Windows Server edition for GUI use  

---

## 🛠️ Tools Used  
<div>
  <a href="https://www.vmware.com/products/workstation-pro.html" target="_blank">
    <img src="https://img.shields.io/badge/-VMware_Workstation_17_Pro-607078?style=for-the-badge&logo=vmware&logoColor=white"/>
  </a>
  <a href="https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2025" target="_blank">
    <img src="https://img.shields.io/badge/-Windows_Server_2025-0078D4?style=for-the-badge&logo=windows&logoColor=white"/>
  </a>
</div>

---

## 📝 Deployment Steps  

### 1. Download the Windows Server 2025 ISO  
- Visit the [Microsoft Evaluation Center](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2025)  
- Download the **ISO** (choose the *Desktop Experience* build if prompted)  
- Optional: verify the hash integrity before installing  

---

### 2. Create the Virtual Machine  
1. **Open VMware Workstation 17 Pro** → *Create a New Virtual Machine*  
2. **Choose:** *Custom (Advanced)*  
3. **Installer:** *I will install the operating system later*  
4. **Guest OS:** Microsoft Windows → *Windows Server 2022/2025 x64*  
5. **VM Name:** `DC01`  
6. **Processors:** 2 CPUs, 2 cores each  
7. **Memory:** 6 GB RAM  
8. **Network Adapter:** NAT  
9. **Controller:** LSI Logic SAS  
10. **Disk Type:** SATA  
11. **Virtual Disk:** New virtual disk (60 GB, split into multiple files)  

💡 *BIOS + SATA is preferred for fewer compatibility issues during setup.*

---

### 3. Attach the ISO  
- Go to **VM Settings → CD/DVD (SATA)**  
- Select **Use ISO image file** → Browse → `Windows_Server_2025.iso`  
- Enable **Connect at power on** → Click **OK**  

---

### 4. Boot and Install Windows Server  
1. Power on the VM  
2. When prompted, press any key to boot from the ISO  
3. Choose the edition:  
   - **Windows Server 2025 Standard Evaluation (Desktop Experience)**  
4. Proceed through:  
   - Language and keyboard setup  
   - License agreement  
   - Administrator password creation  

---

### 5. Post-Install Tasks  
- Rename the server to `DC01`  
- Set a static IP address (recommended for domain controllers)  
- Take a snapshot before promoting it to AD DS  

---

### ✅ Next Steps  
Continue with the **Active Directory Domain Services (AD DS)** installation and domain promotion in the next sub-project.

---

### 👨‍💻 Author
Mario Tagaras | Cyber Security Specialist
