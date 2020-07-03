# Azurepowershell
Powershell script for resourcegroup deployement of vnet. subnet & ubuntu VM
you need to change the paramenters settings like CIDR, Subnet name, VMName, username and password etc.
all the changes should be in the parameters file
To run the command in the power shell, refer the below procedure ,
open the powershell as Administrator
connect to azure by running below command 

Connect-AzAccount

run the below command 

 New-AzResourceGroup `
-Name myResourceGroupDev `
-Location "East US"

save the both file with any name, for me I am saving as per below, run the same command with your file path
$pamvm =  "D:\Coding-AZPowerShell\vmautomationparameteres.json"
$tempvm = "D:\Coding-AZPowerShell\vmautomationtemplate.json"

 New-AzResourceGroupDeployment `
-Name VMvnetDeployement `
-ResourceGroupName myResourceGroupDev `
-TemplateFile $tempvm `
-TemplateParameterFile $pamvm

you will get output as,

DeploymentName          : VMvnetDeployement
ResourceGroupName       : myResourceGroupDev
ProvisioningState       : Succeeded
Timestamp               : 03-07-2020 11:13:16
Mode                    : Incremental
TemplateLink            :
Parameters              :
                          Name                             Type                       Value
                          ===============================  =========================  ==========
                          location                         String                     eastus
                          virtualNetworkName               String                     Test-NSG1
                          resourceGroup                    String                     Test
                          addressSpaces                    Array                      [
                            "10.0.0.0/16"
                          ]
                          ipv6Enabled                      Bool                       False
                          subnetCount                      Int                        2
                          subnet0_name                     String                     Web
                          subnet0_addressRange             String                     10.0.0.0/24
                          subnet1_name                     String                     DB
                          subnet1_addressRange             String                     10.0.1.0/24
                          ddosProtectionPlanEnabled        Bool                       False
                          firewallEnabled                  Bool                       False
                          bastionEnabled                   Bool                       False
                          networkInterfaceName             String                     powershell-test43
                          networkSecurityGroupName         String                     powershell-test-nsg
                          networkSecurityGroupRules        Array                      []
                          subnetName                       String                     Web
                          virtualNetworkId                 String
                          /subscriptions/31502c63-bc9e-4dd2-815b-5c4095cb927c/resourceGroups/myResourceGroupDev/providers/Microsoft.Network/virtualNetworks/Test-NSG1
                          publicIpAddressName              String                     powershell-test1-ip
                          publicIpAddressType              String                     Dynamic
                          publicIpAddressSku               String                     Basic
                          virtualMachineName               String                     powershell-test1
                          virtualMachineComputerName       String                     powershell-test1
                          virtualMachineRG                 String                     myResourceGroupDev
                          osDiskType                       String                     Premium_LRS
                          virtualMachineSize               String                     Standard_B1s
                          adminUsername                    String                     ubuntu
                          diagnosticsStorageAccountName    String                     myresourcegroupdevdia795
                          diagnosticsStorageAccountId      String                     Microsoft.Storage/storageAccounts/myresourcegroupdevdia795
                          diagnosticsStorageAccountType    String                     Standard_LRS
                          diagnosticsStorageAccountKind    String                     Storage

Outputs                 :
                          Name             Type                       Value
                          ===============  =========================  ==========
                          adminUsername    String                     ubuntu

DeploymentDebugLogLevel :
