# NETWORKWALKS-AYEN-B084-PM1-CYBERSECURITY-LAB-SETUP

## 📁 DOWNLOADED VIRTUALBOX ##

Download and install the latest VirtualBox with its corresponding Extension Pack from the Official VirtualBox downloads page.

# Step 1: Configure the NAT Network in VirtualBoxA 
NAT Network allows multiple VMs to access the external network (Internet) as well as communicate securely with each other on the same virtual subnet.
1. Open VirtualBox Manager.
2. Go to the top menu and select File > Preferences (or Tools > Network depending on your VirtualBox version).
3. Select the Network tab, then click on the NAT Networks sub-tab.
4. Click the + (Create) button on the right to add a new NAT network.
5. Select the newly created network (usually named NatNetwork) and click the Wrench/Edit icon:
   
   Network Name: Give it an identifiable name (e.g., LabNet).
   
   Network CIDR: Enter the subnet range (default is 10.0.2.0/24).
   
   Supports DHCP: Ensure this option is checked so VMs automatically obtain IP addresses.
6. Click OK to save the global preferences.


<img width="1247" height="598" alt="image" src="https://github.com/user-attachments/assets/3ac68376-ac78-47b7-980b-ad532f8c8b87" />


  # Step 2: Configure the Kali Linux VM Settings
  
  Next, map your Kali Linux virtual machine to the newly created NAT Network.
  1. Ensure your Kali Linux VM is Powered Off.
  2. Select the Kali Linux VM in the VirtualBox sidebar and click Settings (gear icon).
  3. Navigate to the Network category on the left menu.
  4. Under Adapter 1: Check the Enable Network Adapter box.

     Set Attached to: dropdown to NAT Network.

     Set Name: dropdown to the NAT network you created in Step 1.

 5. Click OK to save the settings.

    <img width="785" height="519" alt="image" src="https://github.com/user-attachments/assets/707377fc-42f3-45e8-bc21-44973aa1b81b" />


   # Step 3: Configure the Static IP Address (10.0.0.2)

1. Open the NetworkManager terminal UI

2. Use the arrow keys to select Edit a connection and press Enter.

3. Select your wired connection (e.g., Wired connection 1 ) and press Enter.

4. Scroll down to IPv4 CONFIGURATION and change Automatic to Manual.

5. Select  next to IPv4 configuration to reveal the fields, then fill them out as follows:

Addresses: 10.0.0.2/24 (Assuming a standard /24 subnet mask; adjust if your CIDR is different)

Gateway: 10.0.0.1 (Your VirtualBox NAT Network gateway, or local router gateway)

DNS Servers: 8.8.8.8 

6. Scroll down to the bottom and click save.

   <img width="1284" height="722" alt="image" src="https://github.com/user-attachments/assets/bb99a4d3-8c00-40ce-bfad-3f51afcebae6" />

