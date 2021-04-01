---
title: 從協力廠商 HIPS 遷移到 ASR 規則
description: 說明如何使用協力廠商主機入侵防護系統 (HIPS) 解決方案以 ASR 規則的方式進行遷移。
keywords: 攻擊面減少規則，asr，asr rules，hips，主機入侵防護系統，保護規則，反入侵，antiexploit，exploit，感染防護，Microsoft Defender for Endpoint，Microsoft Defender ATP
search.product: eADQiWindows 10XVcnh
ms.topic: article
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: lovina-saldanha
ms.author: v-lsaldanha
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.openlocfilehash: ced969fdd3e8b63136f8bd3f043272e76d99bc5e
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476502"
---
# <a name="migrating-from-a-third-party-hips-to-asr-rules"></a>從協力廠商 HIPS 遷移到 ASR 規則

本文可協助您將一般規則對應至 Microsoft Defender for Endpoint。 下表顯示從協力廠商 HIPS 產品遷移至 ASR 規則時的常見問題及案例。

|範圍和動作|過程|作業|檔案/資料夾、登錄機碼/值、進程、服務的範例|攻擊面減少規則|其他建議功能|
|:--|:--|:--|:--|:--|:--|
|所有處理常式：封鎖特定檔案和登錄機碼的建立||檔建立|*.zepto, *.odin, *.locky, *.jaff, *.lukitus, *.wnry, *.krab|ASR 規則會封鎖攻擊技術，而不是 (IOC) 遭到攻破的指示器。 封鎖特定的副檔名並不一定有用，因為它無法防止裝置受損。 只有在攻擊者為負載建立新的分機類型時，才會部分 thwarts 攻擊。|強烈建議您啟用 Microsoft Defender AV，以及雲端保護和行為分析。 建議您使用其他防護，例如 ASR 規則「使用針對勒索軟體的高級防護」。 這為抵禦勒索軟體攻擊提供更大的防護層級。 此外，許多登錄機碼都是由 Microsoft Defender for Endpoint 所監控，例如 ASEP 技術，它會觸發特定警示。 使用的登錄機碼至少需要有本機系統管理員或受信任的安裝程式許可權，才能加以修改。 建議使用已鎖定的環境，其中包含最低的管理帳戶或權利。 您可以啟用其他系統設定，包括「停用非必要角色的 SeDebug」，這是我們較廣的安全性建議的一部分。|
|所有處理常式：封鎖特定檔案和登錄機碼的建立||修改登錄|* \Software \* ，HKCU\Environment\UserInitMprLogonScript，HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATs \* \StartExe，HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File 執行選項 \* \Debugger，HKEY_CURRENT_USER\Software\Microsoft\HtmlHelp Author\location，HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\SilentProcessExit \* \MonitorProcess|ASR 規則會封鎖攻擊技術，而不是 (IOC) 遭到攻破的指示器。 封鎖特定的副檔名並不一定有用，因為它無法防止裝置受損。 只有在攻擊者為負載建立新的分機類型時，才會部分 thwarts 攻擊。|強烈建議您啟用 Microsoft Defender AV，以及雲端保護和行為分析。 建議您使用其他防護，例如 ASR 規則「使用針對勒索軟體的高級防護」。 這為抵禦勒索軟體攻擊提供更大的防護層級。 此外，許多登錄機碼都是由 Microsoft Defender for Endpoint 所監控，例如 ASEP 技術，它會觸發特定警示。 此外，使用的登錄機碼至少需要有本機系統管理員或受信任的安裝程式許可權，才能加以修改。 建議使用已鎖定的環境，其中包含最低的管理帳戶或權利。 您可以啟用其他系統設定，包括「停用非必要角色的 SeDebug」，這是我們較廣的安全性建議的一部分。|
|來自 USB 的不受信任的程式：封鎖從抽取式磁碟磁碟機執行的不受信任程式|*|處理常式執行|*|ASR 規則具有內建的規則，可防止從抽取式磁碟磁碟機啟動不受信任和未簽署的程式：「封鎖從 USB 執行的不受信任的和未簽署的程式」，GUID "b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4"。|請使用 Microsoft Defender for Endpoint 探索其他控制項的 USB 裝置和其他卸除式媒體： [如何使用 Microsoft defender For endpoint 來控制 usb 裝置和其他卸除式媒體](https://docs.microsoft.com/windows/security/threat-protection/device-control/control-usb-devices-using-intune)。 |
|Mshta：封鎖 Mshta 以啟動特定子進程|mshta.exe|處理常式執行|powershell.exe、cmd.exe、regsvr32.exe|ASR 規則不包含任何特定規則，以防止子流程「mshta.exe」。 此控制項位於 Exploit Protection 或 Windows Defender 應用程式控制的匯款內。|啟用 Windows Defender 應用程式控制，以防止完全執行 mshta.exe。 如果您的組織需要使用「mshta.exe」來進行商務應用程式，請設定特定的 Windows Defender Exploit Protection 規則，以防止 mshta.exe 啟動子進程。|
|Outlook：封鎖 Outlook 以啟動子流程|outlook.exe|處理常式執行|powershell.exe|ASR 規則具有內建規則，可防止 Office 通訊應用程式 (Outlook、Skype 和團隊) 啟動子流程：「封鎖 Office communication application 以建立子進程」，GUID "26190899-1602-49e8-8b27-eb1d0a1ce869"。|建議您啟用 PowerShell 受限語言模式，以將攻擊面從 PowerShell 降到最低。|
|Office：封鎖 Office App 以啟動子流程，以及建立可執行檔內容|winword.exe、powerpnt.exe、excel.exe|處理常式執行|powershell.exe，cmd.exe，wscript.exe，mshta.exe，EQNEDT32.EXE，regsrv32.exe|ASR 規則具有內建規則，可防止 Office 應用程式啟動子流程：「禁止所有 Office 應用程式建立子進程」，GUID "D4F940AB-401B-4EFC-AADC-AD5F3C50688A"。|不適用|
|Office：封鎖 Office App 以啟動子流程，以及建立可執行檔內容|winword.exe、powerpnt.exe、excel.exe|檔建立|C:\Users \* \AppData \* *\* ，C:\ProgramData \**，C:\ProgramData，C:\Users，C:\Users \* \* *\* \* AppData\Local\Temp \** \* \* *\** \* \* \* *\* .com，\Downloads C:\Users，\AppData scf. C:\ProgramData，scf，C:\Users\Public，C:\Users，\Desktop \** \* \* \* \* * \*|不適用|
|Wscript.exe：封鎖 Wscript.exe 讀取特定類型的檔|wscript.exe|檔案讀取|C:\Users \* \AppData \* *\**，C:\Users \* \Downloads \* *\**|因為可靠性和效能問題，所以 ASR 規則不具備防止特定程式讀取特定腳本檔案類型的功能。 我們確實有一個規則，可防止可能源自這些案例的攻擊媒介。 規則名稱是「封鎖 JavaScript 或 VBScript 啟動下載的可執行內容」 (GUID "D3E037E1-3EB8-44C8-A917-57927947596D" ) 及「封鎖執行可能模糊的腳本」 (GUID "5BEB7EFE-FD9A-4556-801D-275E5FFC04CC" ) |雖然在這些案例中有特定的 ASR 規則可減輕某些攻擊的情況，但很重要的一點是，請務必注意，AV 功能預設可以透過反惡意軟體掃描介面) AMSI (，即時檢查腳本 (PowerShell、Windows 腳本主機、JavaScript、VBScript 及其他) 。 如需詳細資訊，請參閱下列網址： [反惡意程式碼掃描介面 (AMSI) ](https://docs.microsoft.com/windows/win32/amsi/antimalware-scan-interface-portal)。 |
|Adobe Acrobat：阻止子流程的啟動|AcroRd32.exe，Acrobat.exe|處理常式執行|cmd.exe、powershell.exe、wscript.exe|ASR 規則可讓您封鎖 Adobe Reader，使其無法啟動子進程。 規則名稱為 "封鎖 Adobe Reader，以建立子流程"，GUID "7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c"。|不適用|
|CertUtil：封鎖可執行內容的下載或建立|certutil.exe|檔建立|* .exe|ASR 規則不支援這些案例，因為它們是 Microsoft Defender 防防毒保護的一部分。|Microsoft Defender AV 可防止 CertUtil 建立或下載可執行檔內容。|
|所有處理常式：封鎖處理常式停止重要的系統元件|*|處理常式終止|MsSense.exe、MsMpEng.exe、NisSrv.exe、svchost.exe *、services.exe、csrss.exe、smss.exe、wininit.exe 等等。|ASR 規則不支援這些案例，因為它們受到 Windows 10 內建的安全性保護。|ELAM (及早啟動反惡意程式碼) ，PPL (保護處理常式淺) ，PPL 反惡意軟體淺色，及系統防護。|
|特定進程：封鎖特定啟動處理常式嘗試|「命名您的進程」|處理常式執行|tor.exe、bittorrent.exe、cmd.exe、powershell.exe 等等。|總而言之，ASR 規則並非設計為應用程式管理員運作。|若要防止使用者啟動特定進程或程式，建議使用 Windows Defender 應用程式控制項。 Microsoft Defender for Endpoint File 和 Cert 指示器可以用於事件回應案例中 (不應該視為應用程式控制機制) 。|
|所有處理常式：封鎖 MDATP AV 設定的未授權變更|*|修改登錄|HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\DisableAntiSpyware、HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\Policy Manager\AllowRealTimeMonitoring 等等。|ASR 規則不會涵蓋這些類型的案例，因為它們是 Microsoft Defender for Endpoint 內建保護的一部分。|防篡改保護 (自願加入，從) Intune 進行管理，可防止對 DisableAntiVirus、DisableAntiSpyware、DisableRealtimeMonitoring、DisableOnAccessProtection、DisableBehaviorMonitoring 和 DisableIOAVProtection 登錄機碼進行未經授權的變更 (和更多) 。 |



另請參閱

- [受攻擊面縮小常見問題集](attack-surface-reduction-faq.md)
- [啟用受攻擊面縮小規則](enable-attack-surface-reduction.md)
- [評估受攻擊面縮小規則](evaluate-attack-surface-reduction.md)
