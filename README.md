# Configuring URL Blocking with pfSense                       
In this lab I will be using pfSense to create firewall rules to block/allow specific URLs.


---
# Scenario   
I am the security analyst for a small corporate network. After monitoring the network, I have discovered that several employees are wasting time visiting non-productive and potentially malicious websites. As such, I have added pfBlockerNG to my pfSense device. I now need to configure this feature and add the required firewall rules that allow/block specific URLs and prevent all DNS traffic from leaving the LAN network.

---
# Step 1: Create a rule that blocks all DNS traffic leaving the LAN network
1. Sign into the administrative pfSense account
2. From the menu bar click on the Firewall dropdown and select Rules
3. Select LAN from the network type
<img width="1461" height="301" alt="image" src="https://github.com/user-attachments/assets/8f5560b7-7399-499a-83e6-7bad310d08a2" />
4. Click on either of the Add buttons to create a new rule 

5. Select the block option from the dropdown menu
6. Set the protocol to UDP
<img width="1437" height="404" alt="image" src="https://github.com/user-attachments/assets/ef1256a3-7f8a-4262-a2ef-3f4ff2f111fd" />
7. In the Source category select LAN net from the dropdown menu

8. Under Destination set the Destination Port Range for From and To to use DNS

9. Add a description in the extra options category
<img width="1429" height="596" alt="image" src="https://github.com/user-attachments/assets/8e06f847-e104-437c-bea0-90afe14a70ed" />
10. Click on save and then apply changes.

 


