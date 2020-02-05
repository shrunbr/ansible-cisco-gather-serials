# ansible-cisco-gather-serials
Gather Serial Numbers From Cisco Devices!

**Prerequisites**

 - Ansible 2.7+
 - Cisco IOS Devices
 - Privilege Level 15 access on your IOS devices

**File Customization**
You will need to customize the gather_serials.yml and inventory files to use this playbook.

 - YML File
	 - Set your output file destination under "save output to file" on the "dest" line.
- inventory
	- You will need to add your device hostnames or IPs under the respective category; routers or switches.

**Running the playbook**

When running the playbook you'll get asked to provide device login credentials. These need to match across all devices you're going to hit otherwise you will receive failures. We are assuming with this that you are using RADIUS/TACACS+ authentication giving yourself privilege level 15 access.

Once you have provided credentials the playbook will go out to all specified devices and pull serials numbers. Once it has the serial numbers they all will be dumped into the "serial_numbers.txt" file where you specified your destination under "save output to file" the output will look similar to this.

    # BEGIN ANSIBLE MANAGED BLOCK switch.localnetwork.local
    ['FGGG934SD', 'FZZZ1238S9']
    # END ANSIBLE MANAGED BLOCK switch.localnetwork.local

