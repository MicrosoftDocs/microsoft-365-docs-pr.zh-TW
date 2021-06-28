---
title: 使用攻擊面減少規則，以防止惡意程式碼感染
description: 攻擊面減少規則可協助防止利用應用程式和腳本感染具有惡意程式碼的裝置。
keywords: 攻擊面減少規則，asr，hips，主機入侵防護系統，保護規則，反侵入，antiexploit，exploit，感染防護，Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: oogunrinde, sugamar, jcedola
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.openlocfilehash: eadca063d50bf1f969f1bb247b6e56d8ec46a6e0
ms.sourcegitcommit: 5866e45a6a4e90c661e8f90c91550a9872b68e03
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/28/2021
ms.locfileid: "53169577"
---
# <a name="use-attack-surface-reduction-rules-to-prevent-malware-infection"></a>使用攻擊面減少規則，以防止惡意程式碼感染

**適用於：**

- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="why-attack-surface-reduction-rules-are-important"></a>攻擊面減少規則為何很重要

組織的攻擊麵包括攻擊者可能會損害組織之裝置或網路的所有地方。 減少攻擊面是指保護您組織的裝置和網路，這可讓攻擊者以較少的方式執行攻擊。 在 Microsoft Defender for Endpoint 中設定攻擊面降低規則可協助！

攻擊面減少規則會以特定的軟體行為為目標，例如：

- 啟動可執行檔及腳本，以嘗試下載或執行檔
- 執行模糊或其他可疑的腳本
- 執行在正常的日常工作中，應用程式通常不會啟動的行為

這類軟體行為有時會出現在合法的應用程式中。 不過，這些行為通常會被視為危險，因為它們通常是透過惡意程式碼被攻擊者濫用。 攻擊面減少規則可以限制以軟體為基礎的危險行為，並協助保護您的組織安全。

如需設定攻擊面減少規則的相關資訊，請參閱 [啟用攻擊面降減規則](enable-attack-surface-reduction.md)。

## <a name="assess-rule-impact-before-deployment"></a>在部署之前評估規則影響

您可以在[威脅與弱點管理](/windows/security/threat-protection/#tvm)中開啟該規則的安全性建議，以評估攻擊面降低規則可能會如何影響您的網路。

:::image type="content" source="images/asrrecommendation.png" alt-text="攻擊面降低規則的安全性 reco":::

在 [建議詳細資料] 窗格中，檢查 [使用者影響] 以判斷您的裝置可接受新原則的百分比，以封鎖模式啟用規則，而不會對生產力造成不良影響。

如需支援的作業系統的相關資訊，請參閱「啟用攻擊面降低規則」一文中的 [需求](enable-attack-surface-reduction.md#requirements) 。

## <a name="audit-mode-for-evaluation"></a>評估的審計模式

使用 [稽核模式](audit-windows-defender.md) 評估攻擊面降低規則在啟用時對組織的影響。 請先在稽核模式中執行所有規則，以便了解它們如何影響您的企業營運應用程式。 許多商務營運應用程式都是以有限的安全性考慮來編寫，而且他們可能會以類似惡意程式碼的方式執行工作。 透過監視審核資料並 [新增](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) 必要應用程式的排除專案，您可以在不降低生產力的情況下，部署攻擊面減少規則。

## <a name="warn-mode-for-users"></a>使用者的警告模式

 (**NEW**！ ) 在警告模式功能之前，已啟用的攻擊面降規則可以設定為 [稽核模式] 或 [封鎖模式]。 使用新的警告模式時，每當攻擊面減少規則封鎖內容時，使用者會看到指出內容已封鎖的對話方塊。 對話方塊也會為使用者提供取消封鎖內容的選項。 然後，使用者可以重試其動作，並完成操作。 當使用者取消封鎖內容時，內容會維持在24小時內解除封鎖，然後封鎖簡歷。

警告模式可協助您的組織實施攻擊面降減規則，而不會防止使用者存取他們執行其工作所需的內容。

### <a name="requirements-for-warn-mode-to-work"></a>警告模式的運作需求

在執行下列 Windows 版本的裝置上支援警告模式：

- [Windows 10 版本 1809](/windows/whats-new/whats-new-windows-10-version-1809)或更新版本
- [Windows Server，版本 1809](/windows-server/get-started/whats-new-in-windows-server-1809)或更新版本

使用[Active 模式](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)中的即時保護時，必須執行 Microsoft Defender 防毒軟體。

此外，請確定已安裝[Microsoft Defender 防毒軟體和反惡意軟體更新](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions)。

- 最低平臺版本需求： `4.18.2008.9`
- 最低引擎發行需求： `1.1.17400.5`

如需詳細資訊和若要取得更新，請參閱 [Microsoft Defender 反惡意程式碼平臺的更新](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)。

### <a name="cases-where-warn-mode-is-not-supported"></a>不支援警告模式的情況

當您在 Microsoft 端點管理員中設定三種攻擊面降減規則時，不支援警告模式。  (如果使用群組原則來設定攻擊面降低規則，則會支援警告模式。 ) 在 Microsoft 端點管理員中進行設定時，不支援警告模式的三個規則如下：

- [封鎖 JavaScript 或 VBScript 啟動下載的可執行內容](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) (GUID `d3e037e1-3eb8-44c8-a917-57927947596d`) 
- [透過 WMI 事件訂閱封鎖的封鎖](#block-persistence-through-wmi-event-subscription) (GUID `e6db77e5-3df2-4cf1-b95a-636979351e5b`) 
- [使用針對勒索軟體](#use-advanced-protection-against-ransomware) (GUID 的高級防護 `c1db55ab-c21a-4637-bb3f-a12568109d35`) 

此外，執行舊版本 Windows 的裝置不支援警告模式。 在這種情況下，已設定為在警告模式中執行的攻擊面降規則會以封鎖模式執行。

## <a name="notifications-and-alerts"></a>通知與提醒

每當觸發攻擊面降低規則時，就會在裝置上顯示通知。 您可以使用公司詳細資料和連絡資訊[自訂通知](customize-attack-surface-reduction.md#customize-the-notification)。

此外，當觸發某些攻擊面降低規則時，會產生警示。

您可以在 Microsoft 365 Defender 入口網站 (中查看通知及所產生的任何警示 [https://security.microsoft.com](https://security.microsoft.com)) 先前稱為[Microsoft Defender 資訊安全中心](microsoft-defender-security-center.md)) 的 (。

## <a name="advanced-hunting-and-attack-surface-reduction-events"></a>高級搜尋和攻擊面降低事件

您可以使用高級搜尋來查看攻擊面降低事件。 為了簡化傳入資料的數量，您可以透過高級搜尋查看每小時只有一個唯一的處理常式。 攻擊面降低事件的時間是在一小時內第一次看到的事件。

例如，假設在 2:00 PM 小時內10台裝置上發生攻擊面降低事件。 假設第一個事件發生于2:15，最後是2:45。 使用高級搜尋時，您會看到該事件的一個實例 (，即使它實際發生于10個裝置) 上，而且其時間戳記會是 2:15 PM。

如需有關高級搜尋的詳細資訊，請參閱 [使用高級搜尋主動搜尋威脅](advanced-hunting-overview.md)。

## <a name="attack-surface-reduction-features-across-windows-versions"></a>跨 Windows 版本的攻擊面減少功能

您可以針對執行下列任何版本與 Windows 的裝置，設定攻擊面減少規則：

- Windows 10 專業版，[版本 1709](/windows/whats-new/whats-new-windows-10-version-1709)或更新版本
- Windows 10 企業版，[版本 1709](/windows/whats-new/whats-new-windows-10-version-1709)或更新版本
- Windows伺服器，[版本 1803 (半年通道) ](/windows-server/get-started/whats-new-in-windows-server-1803)或更新版本
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

雖然攻擊面降減規則不需要[Windows E5 授權](/windows/deployment/deploy-enterprise-licenses)，但如果您有 Windows E5，就會取得高級管理功能。 「高級功能」-僅適用于 Windows E5-包括：

- 在[Defender For Endpoint](microsoft-defender-endpoint.md)中可用的監控、分析和工作流程
- [Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center)中的報告和設定功能。

Windows Professional 或 Windows E3 授權無法使用這些高級功能。 不過，如果您有這些授權，您可以使用「事件檢視器」和 Microsoft Defender 防毒軟體記錄檔，以查看攻擊面減少規則事件。

## <a name="review-attack-surface-reduction-events-in-the-microsoft-365-defender-portal"></a>在 Microsoft 365 Defender 入口網站中查看攻擊面降低事件

當警示調查案例中，Defender for Endpoint 提供事件和區塊的詳細報告。

您可以使用 [[高級搜尋](advanced-hunting-query-language.md)]，在[Microsoft 365 Defender](microsoft-defender-security-center.md)中查詢 Defender 的端點資料。 如果您正在執行 [稽核模式](audit-windows-defender.md)，您可以使用高級搜尋來瞭解攻擊面降低規則可能會如何影響您的環境。

範例查詢如下：

```kusto
DeviceEvents
| where ActionType startswith 'Asr'
```

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a>在 Windows 事件檢視器中查看攻擊面降低事件

您可以查看 Windows 事件記錄檔，以查看攻擊面減少規則所產生的事件：

1. 下載 [評估套件](https://aka.ms/mp7z2w) ，並將檔案 *cfa-events.xml* 解壓至裝置上易於存取的位置。

2. 在 [開始] 功能表中輸入文字、*事件檢視器*，以開啟 Windows 事件檢視器。

3. 在 [ **動作**] 下，選取 [匯 **入自訂視圖 ...**]。

4. 從解壓縮的位置選取檔案 *cfa-events.xml* 。 或者， [直接複製 XML](event-views.md)。

5. 選取 [確定]。

您可以建立篩選事件只顯示下列事件的自訂視圖，這些事件都與「受控資料夾存取」有關：

|事件識別碼|描述|
|---|---|
|5007|設定變更時的事件|
|1121|在組塊模式中激發規則時的事件|
|1122|在稽核模式中觸發規則時的事件|

在事件記錄中，列出的攻擊面降低事件的「引擎版本」是由 Defender for Endpoint 所產生，而不是由作業系統產生。 與 Windows 10 的 Defender 已整合，所以此功能可在已安裝 Windows 10 的所有裝置上運作。

## <a name="attack-surface-reduction-rules"></a>受攻擊面縮小規則

下表與子小節分別說明16個攻擊面降低規則。 攻擊面降低規則會依規則名稱依字母順序列出。

如果您是使用群組原則或 PowerShell 來設定攻擊面降低規則，則需要 Guid。 另一方面，如果您使用 Microsoft 端點管理員或 Microsoft Intune，便不需要 guid。

|規則名稱|GUID|File & 資料夾排除|支援的最低作業系統|
|---|:---:|---|---|
|[封鎖濫用的漏洞簽章驅動程式](#block-abuse-of-exploited-vulnerable-signed-drivers)|`56a863a9-875e-4185-98a7-b882c64b5ce5`|支援|[Windows 10，版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本)  |
|[封鎖 Adobe Reader，以建立子流程](#block-adobe-reader-from-creating-child-processes)|`7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`|支援|[Windows 10，版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本|
|[封鎖所有 Office 的應用程式建立子流程](#block-all-office-applications-from-creating-child-processes)|`D4F940AB-401B-4EFC-AADC-AD5F3C50688A`|支援|[Windows 10，版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本|
|[封鎖 Windows 本機安全性群組子系統 (lsass.exe 中的認證竊取) ](#block-credential-stealing-from-the-windows-local-security-authority-subsystem)|`9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`|支援|[Windows 10，版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本|
|[從電子郵件客戶程式和 web 郵件封鎖可執行檔內容](#block-executable-content-from-email-client-and-webmail)|`BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`|支援|[Windows 10，版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本|
|[封鎖可執行檔，除非符合流行、age 或受信任的清單準則](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion)|`01443614-cd74-433a-b99e-2ecdc07bfc25`|支援|[Windows 10，版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本|
|[封鎖可能混淆的腳本執行](#block-execution-of-potentially-obfuscated-scripts)|`5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`|支援|[Windows 10，版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本|
|[從啟動下載的可執行內容封鎖 JavaScript 或 VBScript](#block-javascript-or-vbscript-from-launching-downloaded-executable-content)|`D3E037E1-3EB8-44C8-A917-57927947596D`|支援|[Windows 10，版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本|
|[封鎖 Office 應用程式建立可執行檔內容](#block-office-applications-from-creating-executable-content)|`3B576869-A4EC-4529-8536-B80A7769E899`|支援|[Windows 10，版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本|
|[封鎖 Office 的應用程式將程式碼注入其他進程](#block-office-applications-from-injecting-code-into-other-processes)|`75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`|支援|[Windows 10，版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本|
|[封鎖 Office 通訊應用程式建立子流程](#block-office-communication-application-from-creating-child-processes)|`26190899-1602-49e8-8b27-eb1d0a1ce869`|支援|[Windows 10，版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本|
|[透過 WMI 事件訂閱封鎖持久性](#block-persistence-through-wmi-event-subscription)|`e6db77e5-3df2-4cf1-b95a-636979351e5b`|不支援|[Windows 10，版本 1903](/windows/whats-new/whats-new-windows-10-version-1903) (組建 18362) 或更高版本|
|[封鎖來自 PSExec 和 WMI 命令的進程建立](#block-process-creations-originating-from-psexec-and-wmi-commands)|`d1e49aac-8f56-4280-b9ba-993a6d77406c`|支援|[Windows 10，版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本|
|[封鎖從 USB 執行的不受信任和未簽署程式](#block-untrusted-and-unsigned-processes-that-run-from-usb)|`b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`|支援|[Windows 10，版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本|
|[從 Office 宏封鎖 WIN32 API 通話](#block-win32-api-calls-from-office-macros)|`92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`|支援|[Windows 10，版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本|
|[使用勒索軟體的高級防護](#use-advanced-protection-against-ransomware)|`c1db55ab-c21a-4637-bb3f-a12568109d35`|支援|[Windows 10，版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本|
|

### <a name="block-abuse-of-exploited-vulnerable-signed-drivers"></a>封鎖濫用的漏洞簽章驅動程式

此規則可防止應用程式將有漏洞的簽署驅動程式寫入磁片。 實際上， \- _具有足夠許可權_ \- 才能存取內核的本機應用程式可以利用有漏洞的已簽署驅動程式。 有漏洞的簽章驅動程式可讓攻擊者停用或規避安全性解決方案，最後導致系統受損。

遭到 **濫用的漏洞已簽章驅動程式規則封鎖** ，不會封鎖已存在於已在系統上載入的驅動程式。

>[!NOTE]
>
> 您可以使用 mem OMA-URI 自訂規則的程式 [資訊，來](enable-attack-surface-reduction.md#mem) 設定此規則。
>
> 您也可以使用 [PowerShell](enable-attack-surface-reduction.md#powershell)來設定此規則。
>
> 若要檢查驅動程式，請使用此網站 [提交分析的驅動程式](https://www.microsoft.com/en-us/wdsi/driversubmission)。

所有支援 ASR 的版本都支援此規則;如下：

- [Windows 10 專業版，版本 1709](/windows/whats-new/whats-new-windows-10-version-1709)或更新版本
- [Windows 10 企業版，版本 1709](/windows/whats-new/whats-new-windows-10-version-1709)或更新版本
- [Windows Server，版本 1803 (半年通道) ](/windows-server/get-started/whats-new-in-windows-server-1803)或更新版本
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Intune 名稱： `Block abuse of exploited vulnerable signed drivers`

GUID:：  `56a863a9-875e-4185-98a7-b882c64b5ce5`

### <a name="block-adobe-reader-from-creating-child-processes"></a>封鎖 Adobe Reader，以建立子流程

此規則會封鎖來自 Adobe Reader 的攻擊，使其無法建立處理常式。

透過社交工程或利用方式，惡意程式碼可以下載和啟動有效載荷，並中斷 Adobe Reader。 透過封鎖子流程以供 Adobe Reader 的產生，惡意程式碼嘗試使用它做為向量，便無法散佈。

此規則的引入時間：

- [Windows 10 版本 1809](/windows/whats-new/whats-new-windows-10-version-1809)
- [Windows伺服器，版本1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Intune 名稱： `Process creation from Adobe Reader (beta)`

Configuration Manager 名稱：尚未提供

GUID:： `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`

### <a name="block-all-office-applications-from-creating-child-processes"></a>封鎖所有 Office 的應用程式建立子流程

此規則會封鎖 Office 的應用程式建立子流程。 Office 應用程式包括 Word、Excel、PowerPoint、OneNote 和 Access。

建立惡意的子流程是常見的惡意程式碼策略。 濫用 Office 為向量的惡意程式碼通常會執行 VBA 宏，並利用程式碼下載並嘗試執行更多負載。 不過，某些合法的企業營運應用程式也可能會產生子進程，以用於良性目的;例如，產生命令提示字元或使用 PowerShell 來設定登錄設定。

此規則的引入時間：

- [Windows 10，版本1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows伺服器，版本1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Intune 名稱： `Office apps launching child processes`

Configuration Manager 名稱： `Block Office application from creating child processes`

GUID:： `D4F940AB-401B-4EFC-AADC-AD5F3C50688A`

### <a name="block-credential-stealing-from-the-windows-local-security-authority-subsystem"></a>封鎖從 Windows 本機安全授權子系統偷竊的認證

此規則可鎖定本機安全授權子系統服務 (LSASS) ，以防止認證偷竊。

LSASS 驗證在 Windows 電腦上登入的使用者。 Microsoft Defender Credential Guard in Windows 10 一般會防止嘗試從 LSASS 提取認證。 不過，某些組織無法在其所有電腦上啟用認證防護，因為自訂的智慧卡驅動程式或其他載入至本機安全授權的程式的相容性問題 (LSA) 。 在這些情況下，攻擊者可以使用像是 Mimikatz 的駭客攻擊工具，從 LSASS scrape 純文字密碼和 NTLM 雜湊。

> [!NOTE]
> 在某些應用程式中，此程式碼會列舉所有執行中的程式，並嘗試以詳盡的許可權來開啟這些進程。 此規則會拒絕應用程式的「開啟」動作，並將詳細資料記錄到安全性事件記錄檔。 此規則會產生大量的噪音。 如果您有一個應用程式，只列舉 LSASS，但沒有任何實際的功能影響，便不需要將其新增至排除清單。 這個事件記錄專案本身不一定表示惡意威脅。

此規則的引入時間：

- [Windows 10，版本1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows伺服器，版本1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)

Intune 名稱： `Flag credential stealing from the Windows local security authority subsystem`

Configuration Manager 名稱： `Block credential stealing from the Windows local security authority subsystem`

GUID:： `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`

### <a name="block-executable-content-from-email-client-and-webmail"></a>從電子郵件客戶程式和 web 郵件封鎖可執行檔內容

此規則會封鎖下列檔案類型，以從 Microsoft Outlook 應用程式內開啟的電子郵件，或 Outlook .com 和其他流行的 web 郵件提供者來啟動：

- 可執行檔 (例如 .exe、.dll 或 .scr) 
- 腳本檔案 (例如 PowerShell .ps、Visual Basic .vbs 或 JavaScript .js 檔) 

此規則的引入時間：

- [Windows 10，版本1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows伺服器，版本1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Microsoft 端點管理員CB 1710](/configmgr/core/servers/manage/updates)

Intune 名稱： `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`

Microsoft 端點管理員名稱：`Block executable content from email client and webmail`

GUID:： `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`

> [!NOTE]
> **從電子郵件客戶程式和 web 郵件封鎖可執行檔內容**，具有下列替代描述（取決於您所使用的應用程式）：
>
> - Intune (設定檔) ：執行可執行檔內容 (exe、dll、ps、js、vbs 等 ) 從電子郵件 (郵件) web 郵件用戶端 () 沒有例外。
> - 端點管理員：封鎖電子郵件和郵件傳送用戶端的可執行內容下載。
> - 群組原則：從電子郵件客戶程式和 web 郵件封鎖可執行檔內容。

### <a name="block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion"></a>封鎖可執行檔，除非符合流行、age 或受信任的清單準則

此規則會封鎖可執行檔，例如 .exe、.dll 或 .scr，除非符合下列任一條件，否則不會啟動：

- 傳播：可執行檔位於1000以上的端點上
- Age：已于24小時前發行可執行檔
- 位置：可執行檔會包含在信任的清單或排除清單中

啟動不受信任或未知的可執行檔可能會是危險的，因為如果這些檔案是惡意的，就可能不會做為清除。

> [!IMPORTANT]
> 您必須 [啟用雲端提供的保護](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) 才能使用此規則。
>
> 規則會 **封鎖可執行檔，除非符合** 「具有 GUID 的流行」、「年齡」或「受信任」清單準則， `01443614-cd74-433a-b99e-2ecdc07bfc25` 且不是由系統管理員所指定的狀態。 此規則使用雲端提供的保護，定期更新其信任清單。
>
> 您可以使用資料夾路徑或完全限定的資源名稱來指定個別檔案或資料夾 () 但是您無法指定適用的規則或排除專案。

此規則的引入時間：

- [Windows 10，版本1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows伺服器，版本1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)

Intune 名稱： `Executables that don't meet a prevalence, age, or trusted list criteria`

Configuration Manager 名稱： `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`

GUID:： `01443614-cd74-433a-b99e-2ecdc07bfc25`

### <a name="block-execution-of-potentially-obfuscated-scripts"></a>封鎖可能混淆的腳本執行

此規則會偵測模糊腳本中的可疑屬性。

腳本模糊處理是一種常見的技術，惡意程式碼作者和合法的應用程式都使用它來隱藏知識屬性或減少腳本載入時間。 惡意程式碼作者也會使用模糊處理，使惡意程式碼難以閱讀，這可防止人員和安全性軟體的接近審查。

此規則的引入時間：

- [Windows 10，版本1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows伺服器，版本1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Intune 名稱： `Obfuscated js/vbs/ps/macro code`

Configuration Manager 名稱： `Block execution of potentially obfuscated scripts`

GUID:： `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`

### <a name="block-javascript-or-vbscript-from-launching-downloaded-executable-content"></a>從啟動下載的可執行內容封鎖 JavaScript 或 VBScript

此規則可防止腳本啟動可能已下載的惡意內容。 撰寫在 JavaScript 或 VBScript 中的惡意程式碼通常是可從網際網路取得及啟動其他惡意程式碼的下載宏。

雖然不是常見的企業營運應用程式，但有時會使用腳本下載及啟動安裝程式。

此規則的引入時間：

- [Windows 10，版本1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows伺服器，版本1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Intune 名稱： `js/vbs executing payload downloaded from Internet (no exceptions)`

Configuration Manager 名稱： `Block JavaScript or VBScript from launching downloaded executable content`

GUID:： `D3E037E1-3EB8-44C8-A917-57927947596D`

### <a name="block-office-applications-from-creating-executable-content"></a>封鎖 Office 應用程式建立可執行檔內容

此規則可防止 Office 的應用程式（包括 Word、Excel 及 PowerPoint）從建立潛在的惡意可執行檔內容，封鎖惡意程式碼寫入磁片。

以向量進行濫用 Office 的惡意程式碼可能會嘗試中斷 Office，並將惡意元件儲存至磁片。 這些惡意元件會在電腦重新開機後，在系統上持續保存下來。 因此，此規則會防禦一般的持久性技術。

此規則的引入時間：

- [Windows 10，版本1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows伺服器，版本1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [System Center Configuration Manager](/configmgr/core/servers/manage/updates) (sccm) CB 1710 (SCCM 現在已 Microsoft Endpoint Configuration Manager) 

Intune 名稱： `Office apps/macros creating executable content`

SCCM 名稱： `Block Office applications from creating executable content`

GUID:： `3B576869-A4EC-4529-8536-B80A7769E899`

### <a name="block-office-applications-from-injecting-code-into-other-processes"></a>封鎖 Office 的應用程式將程式碼注入其他進程

此規則封鎖程式碼注入嘗試 Office 的應用程式到其他的處理常式。

攻擊者可能會嘗試使用 Office 的應用程式，透過程式碼注入將惡意程式碼遷移到其他程式中，讓程式碼可以偽裝成一種乾淨的處理常式。

使用程式碼注入，並沒有已知的合法商務目的。

此規則會套用至 Word、Excel 及 PowerPoint。

此規則的引入時間：

- [Windows 10，版本1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows伺服器，版本1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Intune 名稱： `Office apps injecting code into other processes (no exceptions)`

Configuration Manager 名稱： `Block Office applications from injecting code into other processes`

GUID:： `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`

### <a name="block-office-communication-application-from-creating-child-processes"></a>封鎖 Office 通訊應用程式建立子流程

此規則可防止 Outlook 建立子流程，但仍然允許合法 Outlook 函式。

此規則可防止「社交工程」攻擊，並防止在 Outlook 中利用 abusing 弱點的程式碼。 它也會防止攻擊者在使用者的認證遭到破壞時可使用的[Outlook 規則和表單攻擊](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/)。

> [!NOTE]
> 此規則會在 Outlook 中封鎖 DLP 原則提示和工具提示。 此規則只適用于 Outlook 和 Outlook .com。

此規則的引入時間：

- [Windows 10 版本 1809](/windows/whats-new/whats-new-windows-10-version-1809)
- [Windows伺服器，版本1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Intune 名稱： `Process creation from Office communication products (beta)`

Configuration Manager 名稱：無法使用

GUID:： `26190899-1602-49e8-8b27-eb1d0a1ce869`

### <a name="block-persistence-through-wmi-event-subscription"></a>透過 WMI 事件訂閱封鎖持久性

此規則可防止惡意程式碼 abusing WMI 在裝置上取得持久性。

> [!IMPORTANT]
> 檔案與資料夾排除不適用於此攻擊面降規則。

Fileless 威脅使用各種不同的戰術來保持隱藏狀態，以避免在檔案系統中看到，以及取得定期執行控制。 有些威脅可以濫用 WMI 存放庫和事件模型，以保持隱藏狀態。

此規則的引入時間：

- [Windows 10，版本1903](/windows/whats-new/whats-new-windows-10-version-1903)
- [Windows伺服器1903](/windows-server/get-started-19/whats-new-in-windows-server-1903-1909)

Intune 名稱：無法使用

Configuration Manager 名稱：無法使用

GUID:： `e6db77e5-3df2-4cf1-b95a-636979351e5b`

### <a name="block-process-creations-originating-from-psexec-and-wmi-commands"></a>封鎖來自 PSExec 和 WMI 命令的進程建立

此規則會封鎖透過 [PsExec](/sysinternals/downloads/psexec) 和 [WMI](/windows/win32/wmisdk/about-wmi) 所建立的處理常式執行。 PsExec 和 WMI 都可以遠端執行程式碼，因此惡意程式碼會 abusing 此功能以進行命令和控制，或將感染傳播到整個組織的網路。

> [!WARNING]
> 只有在您使用 [Intune](/intune) 或另一個 MDM 解決方案管理裝置時，才使用此規則。 因為此規則會封鎖 Configuration Manager 用戶端用來正確運作的 WMI 命令，所以此規則與管理的[Microsoft Endpoint Configuration Manager](/configmgr)不相容。

此規則的引入時間：

- [Windows 10，版本1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows伺服器，版本1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Intune 名稱： `Process creation from PSExec and WMI commands`

Configuration Manager 名稱：不適用

GUID:： `d1e49aac-8f56-4280-b9ba-993a6d77406c`

### <a name="block-untrusted-and-unsigned-processes-that-run-from-usb"></a>封鎖從 USB 執行的不受信任和未簽署程式

使用此規則時，系統管理員可以防止未簽署或不受信任的可執行檔，從 USB 抽取式磁碟磁碟機（包括 SD 卡）執行。 封鎖的檔案類型包括可執行檔 (例如 .exe、.dll 或 .scr) 

此規則的引入時間：

- [Windows 10，版本1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows伺服器，版本1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)

Intune 名稱： `Untrusted and unsigned processes that run from USB`

Configuration Manager 名稱： `Block untrusted and unsigned processes that run from USB`

GUID:： `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`

### <a name="block-win32-api-calls-from-office-macros"></a>從 Office 宏封鎖 WIN32 API 通話

此規則可防止 VBA 宏呼叫 WIN32 APIs。

OfficeVBA 啟用 WIN32 API 呼叫。 惡意程式碼可能會濫用這項功能，例如 [呼叫 WIN32 APIs 以發動惡意外殼代碼](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) ，而不需直接寫入任何內容。 大多數的組織不依賴在日常運作中呼叫 WIN32 APIs 的功能，即使它們是以其他方式使用宏。

此規則的引入時間：

- [Windows 10，版本1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows伺服器，版本1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Intune 名稱： `Win32 imports from Office macro code`

Configuration Manager 名稱： `Block Win32 API calls from Office macros`

GUID:： `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`

### <a name="use-advanced-protection-against-ransomware"></a>使用勒索軟體的高級防護

此規則可提供額外的保護，以防禦勒索軟體。 它會同時使用用戶端和雲端試探法來判斷檔案是否與勒索軟體類似。 此規則不會封鎖具備下列一項或多項特性的檔案：

- 檔案已在 Microsoft 雲端中找到 unharmful。
- 檔案是有效的簽署檔。
- 檔案的流行不足，無法視為勒索軟體。

這項規則通常會在警告的另一個方面，以防止勒索軟體。

> [!NOTE]
> 您必須 [啟用雲端提供的保護](enable-cloud-protection-microsoft-defender-antivirus.md) 才能使用此規則。

此規則的引入時間：

- [Windows 10，版本1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows伺服器，版本1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)

Intune 名稱： `Advanced ransomware protection`

Configuration Manager 名稱： `Use advanced protection against ransomware`

GUID:： `c1db55ab-c21a-4637-bb3f-a12568109d35`
