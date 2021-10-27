

OCI Migration (Terraform)
============
>**ZConverter Cloud Migration Membership**
>
> **How to use ZConverter Cloud Migration**
>
> **Target VM generation using terraform**

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

1. Before You Begin
To successfully perform this tutorial, you must have the following:
   * An Oracle Cloud Infrastructure account. [See Signing Up for Oracle Cloud Infrastructure](https://docs.oracle.com/en-us/iaas/Content/GSG/Tasks/signingup.htm)
   * A MacOS, Linux, or Windows environment:
   * MacOS
   * Linux (Any distribution)
      - You can install a Linux VM with an **Always Free** Compute shape, on Oracle Cloud Infrastructure:
         +  [Install an Ubuntu VM](https://docs.oracle.com/iaas/developer-tutorials/tutorials/helidon-on-ubuntu/01oci-ubuntu-helidon-summary.htm#create-ubuntu-vm)
         +  [Install an Oracle Linux VM](https://docs.oracle.com/iaas/developer-tutorials/tutorials/apache-on-oracle-linux/01oci-ol-apache-summary.htm#create-oracle-linux-vm)
   * Oracle Cloud Infrastructure Cloud Shell:
      -  [Cloud Shell](https://docs.oracle.com/iaas/Content/API/Concepts/cloudshellintro.htm)
   * Windows 10
      -  [Windows Subsystem for Linux](https://ubuntu.com/wsl) (WSL)
      -  [Git for Windows](https://gitforwindows.org/) to access a Linux VM.

2. Prepare
Prepare your environment for authenticating and running your Terraform scripts. Also, gather the information your account needs to authenticate the scripts.

3. Install Terraform
   Install the latest version of Terraform **v13.0+**:

   * In your environment, check your Terraform version.
      ```script
      terraform -v
      ```

      If you don't have Terraform **v13.0+**, then install Terraform using the following steps.

   * From a browser, go to [Download Latest Terraform Release](https://www.terraform.io/downloads.html).

   * Find the link for your environment and then **copy** the link address. Example for Linux 64-bit:
      ```script
      https://releases.hashicorp.com/terraform/0.13.1/terraform_0.13.1_linux_amd64.zip
      ```

      * IF you use Windows os, Use the cmd command line

   * In your environment, create a temp directory and change to that directory:
      ```script
      mkdir temp
      ```
      ```script
      dc temp
      ```

   * Download the Terraform zip file. Example:
      ```script
      wget https://releases.hashicorp.com/terraform/0.13.1/terraform_0.13.1_linux_amd64.zip
      ```

   * Unzip the file. Example:
      ```script
      unzip terraform_0.13.1_linux_amd64.zip
      ```

   * Move the folder to /usr/local/bin or its equivalent in Mac. Example:
      ```script
      sudo mv terraform /usr/local/bin
      ```

   * Go back to your home directory:
      ```script
      cd
      ```

   * Check the Terraform version:
      ```script
      terraform -v
      ```

      Example: `Terraform v0.13.1`.

4. Create API-Key
   If you created API keys for the Terraform Set Up Resource Discovery tutorial, then skip this step.

   Create RSA keys for API signing into your **Oracle Cloud Infrastructure account**.

   1. **Log in to the Oracle Cloud site and access the user portal.**

      ![Login](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/login/login3.png)  

   2. **Enter the User menu.**

      ![Account User](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/user_menu.png)  

   3. **Choice User Account Name to use.**
      ![Account Users](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/legacy/select_user.png)

   4. **Click api-key in the lower left resource and click Add API Key.**
     ![Api-Key](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/legacy/click_api_key.png)


   5. **Register the API key by selecting the appropriate option. If there are more than three API keys, delete the API key or use a different User Account Name.**

      ![Api-Key](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/legacy/add_api_key.png)

   6. **Copy the results from Configuration File Preview onto the notepad.**

      ![Configuration](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/legacy/config_copy.png)
   
   7. **Select Networking from the menu, then select Virtual Cloud Networks**

      ![Networking-Virtual Cloud Network](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/legacy/network_menu.png)
   
   9. **Choice VCN User Account Name to use**

      ![Select VCM User Account Name](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/legacy/click_vcn.png)

   1. **Choice Subnets Name to use**

      ![Select Subnets Name](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/legacy/click_subnet.png)

   1. **Copy the Subnet OCID onto the notepad**

      ![Subnet OCID](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/legacy/copy_subnet_ocid.png)

5. Install OCI Terraform Data
   Install the **terraform data** you need to make your OCI vm.

   1. **Download [Terraform data](https://www.zconverter.com/Download/oci_terraform.zip)**

   2. **Unzip OCI Terraform data**

      ![OCI terraform data](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/legacy/unzip_oci_terraform.png)
      
6. Start Terraform

   1. **Edit a vars.tfvars File you want to create VM**

      * vars.tfvars data info:
         + tenancy : Use the tenancy noted in API Key creation.
         + user : Use the user noted in API Key creation.
         + key_file : Use the absolute path of private_key downloaded from API Key generation.
         + fingerprint : Use the fingerprint noted in API Key creation.
         + region : Use the region noted in API Key creation.
         + compartment : Tenancy or compartment for that account
         + shape : 
            - Flexible Shapes : VM.Standard.E3.Flex, VM.Standard.E4.Flex, VM.Optimized3.Flex, VM.Standard.A1.Flex
            - Standard Shapes : VM.Standard2.1, VM.Standard2.2, VM.Standard2.4, VM.Standard2.8, VM.Standard2.16, VM.Standard2.24
         + os :
         + os_version : 
            | | Windows2019 | Windows2016 | Windows2012 R2 | Linux8 | Linux7.9 | Linux6.10 | centos8 | centos7 | centos8 | ubuntu20.04 | ubuntu18.04 | ubuntu16.04 |
            |-|-------------|-------------|----------------|--------|----------|-----------|---------|---------|---------|-------------|-------------|-------------|
            | OS | Windows | Windows | Windows | Oracle Linux | Oracle Linux | Oracle Linux  | CentOS | CentOS | CentOS | Canonical Ubuntu | Canonical Ubuntu | Canonical Ubuntu |
            | OS_Version | Server 2019 Standard | Server 2016 Standard | Server 2012 R2 Standard | 8 | 7.9 | 6.10 | 8 | 7 | 6 | 20.04 | 18.04 | 16.04 |
         + block_volume_count : Number of volumes on server you want to create
         + block_volume_size : Size of volume on server you want to create
         + block_volume_diskplay_name : Name of volume on server you want to create
         + blcok_volume_device_path : Specifies the path to the disk when you add it to the Linux family operating system.
         + diskplay_name : Name of Server you want to
         + subet_ocid : Use the account's subnet_ocid.
         + user_data_path :
            - Enter the path to the txt file in the scripts folder of the downloaded oci_terraform. 
            - Use the file oci_linux_cloud_init_txt for Linux-like operating systems and the file oci_windows_cloud_init_txt for Windows-like operating systems.
         + ssh_public_key_path : Linux-like operating systems require the file path of the user's ssh_public key.
         + ocpus : You must enter the number of CPUs when using Flexible_shape. The range is from 1 to 64.
         + memory_in_gbs : When using Flexible_shape, you must select memory capacity. The range is from cpu count to 1024.

      ![vars.tfvars example](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/legacy/vars.tfvars.png)

   2. **Start CMD**

      ![cmd](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/legacy/cmd.png)

   3. **Go to the file path of Terraform.exe and Initialize the working directory containing the terraform configuration file.**

      ```script
      terraform.exe -chdir={terraform data file path} init
      ```

      **Note**
      * -chdir : The usual way to run Terraform is to first switch to the directory containing the `.tf` files for your root module (for example, using the `cd` command), so that Terraform will find those files automatically without any extra arguments.

      ![terraform init](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/legacy/terraform_init.png)
   
   4. **Creates an execution plan. By default, creating a plan consists of:**

      * Reading the current state of any already-existing remote objects to make sure that the Terraform state is up-to-date.
      * Comparing the current configuration to the prior state and noting any differences.
      * Proposing a set of change actions that should, if applied, make the remote objects match the configuration.

      ```script
      terraform.exe -chdir={terraform data file path} plan -var-file={vars file with user specified name}
      ```

      **Note**
      * -var-file : Sets values for potentially many [input variables](https://www.terraform.io/docs/language/values/variables.html) declared in the root module of the configuration, using definitions from a ["tfvars" file](https://www.terraform.io/docs/language/values/variables.html#variable-definitions-tfvars-files). Use this option multiple times to include values from more than one file.
      * The file name of vars.tfvars can be changed.

      ![terraform plan](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/legacy/terraform_plan.png)

   5. **Executes the actions proposed in a Terraform plan.**

      ```script
      terraform.exe -chdir={terraform data file path} apply -var-file={vars file with user specified name} -auto-approve
      ```
      **Note**
      * -auto-approve : Skips interactive approval of plan before applying. This option is ignored when you pass a previously-saved plan file, because Terraform considers you passing the plan file as the approval and so will never prompt in that case.

      ![terraform apply](https://raw.githubusercontent.com/zconverter/ZCM-legacy/master/image/legacy/terraform_apply.png)

 


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
