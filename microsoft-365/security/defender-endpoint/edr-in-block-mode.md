---
title: 封鎖模式中的端點偵測和回應
description: 深入瞭解封鎖模式中的端點偵測和回應
keywords: Microsoft Defender for Endpoint，mde，EDR 以封鎖模式，被動模式封鎖
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.date: 05/05/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: d7ab8afd1d643933dc71a5bef1385b9ab95b553f
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245801"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>在封鎖模式中) 的端點偵測和回應 (EDR

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>封鎖模式中的 EDR 為何？

[端點偵測和回應](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) (EDR) 在封鎖模式中時，即使 Microsoft Defender 防毒軟體是以被動模式執行，也可以保護惡意的惡意資料。 開啟時，以封鎖模式 EDR 會封鎖在裝置上偵測到的惡意的偽像或行為。 block 模式中的 EDR 會在幕後運作，以修正偵測到破壞後偵測到的惡意作品。 

組塊模式中的 EDR 也會與[威脅 & 弱點管理](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)整合。 組織的安全性小組會取得[安全性建議](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)，以在封鎖模式中開啟 EDR （如果尚未啟用）。 

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="在封鎖模式中開啟 EDR 的建議":::

> [!NOTE]
> 若要取得最佳保護，請務必 **[部署 Microsoft Defender For Endpoint 基準](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)**。

## <a name="what-happens-when-something-is-detected"></a>偵測到某項時會發生什麼情況？

當以封鎖模式開啟 EDR，且偵測到惡意的專案時，Microsoft Defender 會封鎖和 remediates 該專案。 您會在重要訊息 [中心](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#check-activity-details-in-action-center)看到偵測 **狀態為「** 已 **封鎖**」或「已完成」動作。

下圖顯示以封鎖模式 EDR 所偵測到並封鎖的未預期軟體實例：

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="在封鎖模式中 EDR 偵測到某項":::


## <a name="enable-edr-in-block-mode"></a>在封鎖模式中啟用 EDR

> [!IMPORTANT]
> 在封鎖模式中開啟 EDR 之前，請確定符合[需求](#requirements-for-edr-in-block-mode)。

1. 移至 Microsoft Defender 資訊安全中心 ([https://securitycenter.windows.com](https://securitycenter.windows.com)) 並登入。 

2. 選擇 [**設定**  >  **高級功能**]。

3. **在塊狀模式中開啟 EDR**。

> [!NOTE]
> 在組塊模式中 EDR 只能在 Microsoft Defender 資訊安全中心中開啟。 您無法使用登錄機碼、Intune 或群組原則，在封鎖模式中啟用或停用 EDR。

## <a name="requirements-for-edr-in-block-mode"></a>封鎖模式中 EDR 的需求

|需求  |詳細資料  |
|---------|---------|
|權限 |在[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)中指派全域管理員或安全性管理員角色。 請參閱 [基本許可權](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/basic-permissions)。 |
|作業系統     |下列其中一個版本： <br/>-Windows 10 (所有版本)  <br/>-Windows Server，版本1803或更新版本 <br/>-Windows Server 2019  <p>**附注**： Windows Server 2016 上不支援封鎖模式中的 EDR。       |
|WindowsE5 登記     |WindowsE5 包含在下列訂閱中： <br/>-Microsoft 365 E5 <br/>-Microsoft 365 E3 搭配身分識別 & 威脅防護服務 <br/><br/>請參閱[每個計畫的](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)[元件](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-overview?view=o365-worldwide&preserve-view=true#components)和功能。       |
|Microsoft Defender 防毒軟體  |必須以主動模式或被動模式安裝和執行 Microsoft Defender 防毒軟體。  (您可以在非 Microsoft 防病毒方案旁使用 Microsoft Defender 防毒軟體。 ) [確認 Microsoft Defender 防毒軟體為主動或被動模式](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode)。 |
|雲端提供的保護 |請確定已設定 Microsoft Defender 防毒軟體，讓[已啟用雲端傳遞的保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus)。 |
|Microsoft Defender 防毒軟體反惡意程式碼用戶端 |請確定您的用戶端是最新版本。 使用 PowerShell，以系統管理員身分執行 [MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) Cmdlet。 在 **AMProductVersion** 行中，您應該會看到 **4.18.2001.10** 或更新版本。 |
|Microsoft Defender 防毒軟體引擎 |請確定您的引擎是最新版本。 使用 PowerShell，以系統管理員身分執行 [MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) Cmdlet。 在 **AMEngineVersion** 行中，您應該會看到 **1.1.16700.2** 或更新版本。 |

> [!IMPORTANT]
> 若要取得最佳保護值，請確定您的防病毒方案已設定為接收定期更新和基本功能，以及您的 [排除已設定](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)。 在封鎖模式中 EDR 會考慮針對 Microsoft Defender 防毒軟體所定義的排除專案。

## <a name="frequently-asked-questions"></a>常見問題集 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-even-when-i-have-microsoft-defender-antivirus-running-on-devices"></a>即使在裝置上執行 Microsoft Defender 防毒軟體，我是否需要在封鎖模式中開啟 EDR？

建議您將 EDR 置於封鎖模式，不論 Microsoft Defender 防毒軟體是以被動模式還是以主動模式執行。 在封鎖模式中 EDR 會提供另一個與 Microsoft Defender for Endpoint 的防禦層。 它可讓 Defender for Endpoint 根據破壞後的行為 EDR 偵測採取動作。 

### <a name="will-edr-in-block-mode-have-any-impact-on-a-users-antivirus-protection"></a>會在封鎖模式中 EDR 是否會影響使用者的病毒防護？ 

在封鎖模式中 EDR 不會影響使用者裝置上執行的協力廠商防防毒保護。 如果主要防病毒解決方案未接任何問題，或發生破壞後的情況，則 EDR 以封鎖模式運作。 在封鎖模式中 EDR 的運作方式與[被動模式 Microsoft Defender 防毒軟體](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)相同，但也會封鎖和 remediates 偵測到的惡意專案或行為。 

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>為什麼我需要讓 Microsoft Defender 防毒軟體保持最新狀態？ 

由於 Microsoft Defender 防毒軟體偵測和 remediates 惡意專案，因此務必將其保持在最新狀態。 為使封鎖模式中的 EDR 生效，它會使用最新的裝置學習模型、行為偵測和試探法。 功能 [終結點](https://docs.microsoft.com/windows/security/threat-protection) 堆疊功能的運作方式是以整合方式運作。 若要取得最佳防護值，您應該將 Microsoft Defender 防毒軟體保持最新狀態。  

### <a name="why-do-we-need-cloud-protection-on"></a>我們為何需要雲端保護開啟？ 

需要 Cloud protection 才能開啟裝置上的功能。 雲端防護功能可讓 [Defender For Endpoint](https://docs.microsoft.com/windows/security/threat-protection) ，根據我們的廣泛和深度安全性情報，以及行為和裝置教學模型，提供最新和最佳的保護。

### <a name="how-do-i-set-microsoft-defender-antivirus-to-passive-mode"></a>如何將 Microsoft Defender 防毒軟體設定為被動模式？

請參閱[Enable Microsoft Defender 防毒軟體，並確認它是以被動模式](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/switch-to-microsoft-defender-setup#enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode)。

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>如何確認 Microsoft Defender 防毒軟體處於主動或被動模式？

若要確認 Microsoft Defender 防毒軟體是否以主動或被動模式執行，您可以在執行 Windows 的裝置上使用命令提示字元或 PowerShell。

#### <a name="use-powershell"></a>使用 PowerShell

1. 選取 [開始] 功能表，開始輸入 `PowerShell` ，然後在結果中開啟 Windows PowerShell。

2. 類型 `Get-MpComputerStatus`。

3. 在結果清單中的 [ **AMRunningMode** ] 列中，尋找下列其中一個值：   
   - `Normal`
   - `Passive Mode`  
   - `SxS Passive Mode`

若要深入瞭解，請參閱 [MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus)。

#### <a name="use-command-prompt"></a>使用命令提示字元

1. 選取 [開始] 功能表，開始輸入 `Command Prompt` ，然後在結果中開啟 Windows 命令提示字元。

2. 類型 `sc query windefend`。

3. 在結果清單中的 [ **狀態** ] 列中，確認服務正在執行中。

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>停用封鎖模式中的 EDR 需要多少時間？

如果您選擇在封鎖模式中停用 EDR 可能需要30分鐘的時間，系統才會停用此功能。

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a>在 Windows Server 2016 上支援的封鎖模式中 EDR 嗎？

錯誤。 在封鎖模式中 EDR 為下列 Windows 版本支援的版本：

- 所有版本 Windows 10 () 
- Windows伺服器、版本1803或更新版本 
- Windows Server 2019 

## <a name="see-also"></a>另請參閱

- [技術 Community 博客：在封鎖模式中引入 EDR：在其蹤跡中停止攻擊](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [行為封鎖和包含專案](behavioral-blocking-containment.md)
- [相得益彰：Microsoft Defender 防毒軟體與適用於端點的 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/why-use-microsoft-antivirus)

