Create a Microsoft Online shell to manage Office 365
====

###Install Module
Download the [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://www.microsoft.com/en-us/download/details.aspx?id=41950) and install it.

Download the [Microsoft Azure Active Directory Module for Windows PowerShell](http://connect.microsoft.com/site1164/Downloads/DownloadDetails.aspx?DownloadID=59185) and install it.


###Create MSOnlineStartup.ps1 without credential file
**This options will prompt you for a password each time you launch the shortcut**

``$UserCredential = Get-Credential``  
``Connect-MsolService -Credential $UserCredential``

###Create MSOnlineStartup.ps1 that uses a credential file
**This option will auto log you in using your O365 credntials**  

``$UserCredential = Import-CliXML -path ".\credentials.creds"``  
``Connect-MsolService -Credential $UserCredential``

###Create credential file
``$password = ConvertTo-SecureString -string "<your password>" -AsPlainText -Force``  
``New-Object System.Management.Automation.PSCredential("<user name>", $password) | Export-CliXml -path "$env:userprofile\Scripts\MSOnline\credentials.cred"``

###Create Shortcut
powershell.exe -noexit import-module msonline; .\msonlinestartup.ps1

The startup folder should be the path to the folder where you saved msonlinestartup.ps1 file.
