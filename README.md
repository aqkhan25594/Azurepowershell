# Azurepowershell
Powershell script for resourcegroup deployement of vnet. subnet & ubuntu VM
you need to change the paramenters settings like CIDR, Subnet name, VMName, username and password etc.
all the changes should be in the parameters file
To run the command in the power shell, refer the below procedure ,
open the power
run the below command 
 New-AzResourceGroup `
>>   -Name myResourceGroupDev `
>>   -Location "East US"
