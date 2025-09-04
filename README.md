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
5. For action select the **Block** from the dropdown menu  
6. Set the protocol to **UDP**
   
<img width="1437" height="404" alt="image" src="https://github.com/user-attachments/assets/ef1256a3-7f8a-4262-a2ef-3f4ff2f111fd" />

7. In the Source category select **LAN net** from the dropdown menu
8. Under Destination set the Destination Port Range for From and To to use **DNS(53)**
9. Add a description in the extra options category
    
<img width="1429" height="596" alt="image" src="https://github.com/user-attachments/assets/8e06f847-e104-437c-bea0-90afe14a70ed" />

10. Click on save and then apply changes.

# Step 2: Create a rule that allows all DNS traffic going to the LAN network
1. Once against click on either of the Add buttons
2. Ensure that the Action is set to **Pass**
3. Set the protocl to **UDP**
   
<img width="1419" height="471" alt="image" src="https://github.com/user-attachments/assets/2252e76c-2906-43bc-b27b-80b89bf89b79" />

4. Under Destination select **LAN net** from the drop down menu
5. Also in the Destination category set the Destination Port Range for From and To to use **DNS(53)**
6. Add a description in the extra options category
   
<img width="1442" height="473" alt="image" src="https://github.com/user-attachments/assets/5d46dcb0-2dc8-4edc-ba85-07cf1b2c1979" />

7. Click on save and then apply changes.

# Step 3: Arrange the firewall rules in order for functionality  
1. Drag the block rule to the bottom
2. Drag the allow rule in between the block and the Anti-Lockout Rule

<img width="1447" height="446" alt="image" src="https://github.com/user-attachments/assets/307d3c39-2e3b-4972-b201-1d5131bf265c" />

# Step 4: Enable pfBlockerNG
1. From the menu bar click on the Firewall dropdown and select pfBlockerNG
2. Check the Enable pfBlockerNG box
3. Scroll to the bottom of the page and select **Save**
   
<img width="1460" height="255" alt="image" src="https://github.com/user-attachments/assets/9d2253a2-e823-4309-928a-78144e707f7a" />

# Step 5: Enable and configure DNS block lists
1. From the pfBLockerNG page select **DNSBL**
2. Check the Enable DNSBL box
3. Enter **192.168.0.0** for the Virtual IP

<img width="1422" height="584" alt="image" src="https://github.com/user-attachments/assets/df00ccd5-5085-4ffa-a15b-1b52ebcbaced" />

4. Expand the TLD Blacklist at the bottom of the page
5. Enter the URLs that will be Blacklisted

<img width="1422" height="264" alt="image" src="https://github.com/user-attachments/assets/b187d6b5-e500-432c-8db4-2046f512acc3" />

6. Expand TLD Whitelist
7. Enter the URLs that will be Whitelisted

<img width="1421" height="293" alt="image" src="https://github.com/user-attachments/assets/9e8592c7-18da-459d-b2c8-662c9aee4c06" />

8. Select **Save** to confirm the changes

   
   
 


