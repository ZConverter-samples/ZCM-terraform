
OCI Migration (Legacy)
============
>**ZConverter Cloud Migration Membership**
>
> **How to use ZConverter Cloud Migration**
>
> **Target VM generation**
>
> **Migration from Source VM to Target VM**

## ZConverter Cloud Migration Membership

   1. **Access https://www.z-cloud.net/ through a web browser.**

![z-cloud_login_page](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/z-cloud/login_page.png)

   2. **Click "Register a new membership" and proceed with membership registration.**

![join](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/z-cloud/join.png)



## How to use ZConverter Cloud Migration

   1. **Click the target platform you want to migrate from "Cloud Migration" in the left menu.**
      
   ![menu](https://raw.githubusercontent.com/zconverter/ZCM-legacy/539f47f7e5e6e9534f9b31cd82f484af72df87ee/image/z-cloud/menu.png)

2. **Register on the source server.**
      
	* **ZConverter Cloud Source Agent installation.**

	* **You must register a source or target server for a migration operation, or install a zconverter cloud agent on the server for communication between the source or target server and the zconverter management server.**

	* **Download the Source Agent installation file corresponding to the source server's OS (Windows or Linux) from the "Download Agent" panel.**

	![menu](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/z-cloud/download_source_agent.png)
	
	1. **Windows Server**
			
		* **Remote access to the source server and copy the downloaded agent installation file to the source server.**

			![mst_win](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/z-cloud/mst_win.png)

		* **After running the installation file, select the installation language and click OK.**
		
			![select_lengage](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/z-cloud/select_lengage.png)

		* **Click "next"**
		
			![click_next](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/z-cloud/click_next.png)

		* **Click "I Agree"**
		
			![click_agree](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/z-cloud/click_agree.png)

		* **Click "Install"**
		
			![click_install](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/z-cloud/click_install.png)

		* **When the settings window appears, enter or select the following information.**
			* **Connect option : Choose "Public ZConverter SaaS(http://www.z-cloud.net)"**
			* **Agent mode : "Source"**
			* **User Information : Enter the account information you are currently accessing.**

				![setting](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/z-cloud/source_agent_setting.png)
			
	2. **Linux Server**

		* **SSH access to the source server, and copy the downloaded agent installation file to the /tmp directory of the source server.**

		* **Proceed with the installation through the following command.**

			![setting](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/z-cloud/linux_cmd.png)
			
			```script
			cd /tmp
			tar zxvf ZConverter_CloudSourceClient_Setup_RedHat_x86_V3.0_Build_3005.tar.gz
			cd zconverter_install_source
			```
			
		* **./install.sh command to proceed with the installation.**
			
		* **This is where the agent is to be installed. If you want to install it on a different path, enter that path. The default installation route is /ZConverteragent.**

			![setting](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/z-cloud/lin_install.sh.png)
			
		* **This is the type selection of ZConverter Cloud Migration.  
		
			If you use Public ZCM, choose Item 1, and if you use Private ZCM, select Item 2 and enter the IP of that ZCM.**
			
			![setting](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/z-cloud/lin_cmd_set1.png)
		
		* **This is the part where you enter the account of ZCM that you are currently using.**
			
			![setting](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/z-cloud/lin_cmd_set2.png)
		
		* **When the installation is complete as shown in the following screen, close the connection with the server and return to the z-cloud.net web portal.**
			
			![setting](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/z-cloud/lin_cmd_set3.png)
			
			![setting](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/z-cloud/lin_cmd_set4.png)
3. **Register a source server.**
	
	* **Click the "Load a server list" button to bring the server where the source agent is installed to the list.**
	
		![setting](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/z-cloud/register_a_source_server.png)
	
	* **Please check the connection status between the source server's agent and the ZConverter Cloud Management server through the leftmost icon in the server list. If the connection is disconnected, it is displayed as a red icon, and if the migration proceeds to this state, it may cause an error.**

		![setting](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/z-cloud/source_server_error.png)
	
	* **Click on the server to migrate, and select a source server imaging method in the "Create or select a source image" panel.**
		
		* **"Create a new image" option: Select if you create and migrate a new image of the server.**
		
		* **"Use an listing image" option: Select if you are migrating an existing server image.**
		
		![setting](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/z-cloud/register_a_source_server1.png)
		
		* **Check the disk to be migrated.**
		
		* **In the "Option" panel, select the type and path of the source image storage. 
		(The source image storage is used to store the image of the source server.)**
			* **"Basic" type: Local type storage that is created within the source server and stores images.**
				* We recommend creating a repository on a disk other than the disk to be migrated (when migrating Windows) or creating a repository in the root directory (when migrating Linux).
			* **"Advanced" type: Storage on a remote server. You can select a storage or other network storage within the target server.**
				* Select the "Target Repository" menu if you want to create a repository within the target server to store the source image.
		* **Click "next".**
		![setting](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/z-cloud/register_a_source_server2.png)


## Target VM generation

   1. **Log in to the Oracle Cloud site and access the user portal.**

      ![Login](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/login/login3.png)  

   2. **Enter the Instance menu.**

      ![Enter_instance_menu](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/legacy/menu(instance).png)  

   3. **Click Create instance button**
      ![create_instance_button](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/legacy/create_instance.png)

   4. **Please choose the OS and shape you want to create.**

      ![Api-Key](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/legacy/choice_os_and_shape.png)

   5. **If the selected OS is Linux series, the ssh key must also be registered.**
     ![use_ssh_key](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/legacy/use_ssh_key.png)

   6. **Enter the Block Volumes menu.**

      ![block-menu](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/legacy/block_volume(menu).png)

   7. **Click Create Block Volume button**
     ![create_block_volume](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/legacy/block_volume_create.png)
   
   8. **Create blocks according to the options you need.**
     ![block_option](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/legacy/block_volume_create_option.png)
   
   9. **Go back to the instance window and click the name of the instance you created.**

![attach_block](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/legacy/attach_block.png)

   10. **In the lower left resource, click Attach block volume in the Attached block volumes column.**

![attach_block_volume](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/legacy/attach_block1.png)

   11. **Connect pre-generated blocks. In the case of Linux series of OS, the device path must be set. 
(left photo: Linux, right photo: windows)**
     ![attach_block](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/legacy/attach_block_linux_and_winows.png)

12.  **Register on the target server.**
		
		* **ZConverter Cloud Target Agent installation**
			
			- Download the Target Agent installation file corresponding to the target server's OS (Windows or Linux) from the "Download Agent" panel at the top of the page.
				
				![attach_block](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/z-cloud/target_agent_install.png)
				
			-  **Windows Server**
				
				- The target agent installation procedure is the same as for source agent installation.
				
				- After remote access to the target instance, copy the downloaded agent installation file to the target instance. The subsequent installation procedure proceeds the same as the second process of "How to use ZConverter Cloud Migration."
			
			-  **Linux Server**
					
				- SSH access to the target server and copy the downloaded agent installation file to the /tmp directory of the target server.
					
				- Proceed with the installation through the following command.
				
					![attach_block](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/z-cloud/target_agent_install_lin1.png)
				
				```script
				cd /tmp
				tar zxvf ZConverter\_CloudTargetClient\_Setup\_RedHat\_x86\_V3.0\_Build\_3005.tar.gz
				#(The file name may be different. Please enter the exact file name of the downloaded agent installation file.)
				cd zconverter\_install\_target
				```
			
				- Enter the ./install.sh command to proceed with the installation.
			
				- This is where the agent is to be installed. If you want to install it on a different path, enter that path. The default installation route is /ZConverteragent.
			
					![attach_block](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/z-cloud/target_agent_install_lin2.png)
				
				- This is the type selection of ZConverter Cloud Migration. If you use Public ZCM, choose Item 1, and if you use Private ZCM, select Item 2 and enter the IP of that ZCM.
				
					![attach_block](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/z-cloud/target_agent_install_lin3.png)
					
				- This is the part where you enter the account of the ZCM you are currently using.
				
					![attach_block](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/z-cloud/target_agent_install_lin4.png)
					
				- When the installation is complete as shown in the following screen, terminate access to the server and return to the z-cloud.net web portal.
				
					![attach_block](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/z-cloud/target_agent_install_lin5.png)
				
					![attach_block](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/z-cloud/target_agent_install_lin6.png)

13.  **Register on the target server.**
	
		- Click the "Load a server list" button to retrieve the server on which the target agent is installed.
	
			![attach_block](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/z-cloud/target_server_register_1.png)
	
		- Please check the connection status between the source server's agent and the ZConverter Cloud Management server through the leftmost icon in the server list. When the connection is disconnected, it is displayed as a red icon, and if you proceed with the migration to this state, it may cause an error.
	
			![attach_block](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/z-cloud/target_server_register_2.png)

		- Click the migration target server in the target server list to retrieve disk information.

		- Map the migration target disk of the source server to the "Mapping to the source server" item of the same disk drive as the migration target disk of the source server.

			![attach_block](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/z-cloud/target_server_register_3.png)

		- In the "Target Repository" panel, select the type and path of the image repository.

			- "Basic" Type : Select this option when the source image repository is set to the "Basic" type or "Advanced" type "Target Repository" menu.

				※ The target repository must be created on a drive other than the drive mapped to the source server (**Windows** migration), or on the /ZConverter/ZConverter path 				(**Linux** migration).

			- "Advanced" type: Select this option if the source image store is set to "Advanced" type of network store (please select the same network store selected as the source image store).

				![attach_block](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/z-cloud/target_server_register_4.png)
  
		- In the "Replication Option" panel, set the target server IP and port to which the source image is to be transmitted.
	
			- Target IP : Select the authorized IP of the target server (if not on the list, please press the "Add IP" button to add it).
	
			- Replication Port : Sets the port number to connect when sending the image (default: 50005).

		- Set other migration options in the "Other Option" panel.

			- Hypervisor : Select the virtual device driver type for the cloud instance.

			- Kernel update : Check if you want to update the kernel version of the server. (When you migrate Linux)

			- Encryption (AES256) : Select if you want to apply data encryption during migration.

			- After job script : Register the script file to be executed after migration is completed. (Only .cmd or .sh files can be registered.)

		- Click "next".

			![attach_block](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/z-cloud/target_server_register_5.png)

		- Press the "OK" button to start the migration.

			![attach_block](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/z-cloud/target_server_register_6.png)

		- When the migration operation starts, it automatically goes to the "Monitoring Job" page.

			![attach_block](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/z-cloud/target_server_register_7.png)
