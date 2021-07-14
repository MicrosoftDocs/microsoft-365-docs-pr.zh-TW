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
ms.date: 07/13/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 1915a57becb1cba14605f4512ff123c1bca846bb
ms.sourcegitcommit: 4046c2c390851dffcdb430e1ba38c4df23fe2e69
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/13/2021
ms.locfileid: "53415596"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>在封鎖模式中) 的端點偵測和回應 (EDR

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>封鎖模式中的 EDR 為何？

[Endpoint 偵測和 response](overview-endpoint-detection-response.md) (EDR) 在封鎖模式中，當 Microsoft Defender 防毒軟體不是主要防病毒產品且以被動模式執行時，可提供對惡意專案的保護。 EDR 以封鎖模式 remediates 使用 EDR 偵測到的惡意專案。 主要的非 Microsoft 防病毒產品可能已錯過這類專案。 block 模式中的 EDR 會在幕後運作，以在裝置上修正偵測到的惡意專案（遭到破壞）。 

> [!IMPORTANT]
> 當 Microsoft Defender 防毒軟體即時保護啟用時，封鎖模式中的 EDR 不會提供所有可用的保護。 所有依賴 Microsoft Defender 防毒軟體成為使用中防病毒方案的功能將無法運作，包括下列主要範例： 
> 
> - 當 Microsoft Defender 防毒軟體處於被動模式時，就無法使用即時保護（包括存取掃描）。 若要深入瞭解即時保護原則設定，請參閱 **[Enable and configure Microsoft Defender 防毒軟體 always on protection](configure-real-time-protection-microsoft-defender-antivirus.md)**。
> - 僅當 Microsoft Defender 防毒軟體以主動模式執行時，才可使用 **[網路保護](network-protection.md)** 和 **[攻擊面降規則](attack-surface-reduction.md)** 等功能。 
> 
> 您的非 Microsoft 防病毒解決方案應該提供這些功能。 

封鎖模式中 EDR 會與[威脅 & 弱點管理](next-gen-threat-and-vuln-mgt.md)整合。 組織的安全性小組會取得[安全性建議](tvm-security-recommendation.md)，以在封鎖模式中開啟 EDR （如果尚未啟用）。 

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="在封鎖模式中開啟 EDR 的建議":::

> [!TIP]
> 若要取得最佳保護，請務必 **[部署 Microsoft Defender For Endpoint 基準](configure-machines-security-baseline.md)**。

## <a name="what-happens-when-something-is-detected"></a>偵測到某項時會發生什麼情況？

當以封鎖模式開啟 EDR，且偵測到惡意的專案時，Microsoft Defender 會封鎖和 remediates 該專案。 您的安全性作業小組會在重要訊息 [中心](respond-machine-alerts.md#check-activity-details-in-action-center)看到 **偵測為已** 完成的 **動作的偵測** 狀態。

下圖顯示以封鎖模式 EDR 所偵測到並封鎖的未預期軟體實例：

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="在封鎖模式中 EDR 偵測到某項":::


## <a name="enable-edr-in-block-mode"></a>在封鎖模式中啟用 EDR

> [!TIP]
> 在封鎖模式中開啟 EDR 之前，請確定符合[需求](#requirements-for-edr-in-block-mode)。

1. 移至 Microsoft 365 Defender 入口網站 ([https://security.microsoft.com/](https://security.microsoft.com/)) 並登入。 

2. 選擇 [**設定**  >  **端點**  >  **一般**  >  **高級功能**]。

3. 向下滾動，然後在 **block 模式中啟用 EDR 的** urn。

> [!NOTE]
> 在封鎖模式中 EDR 只能在 Microsoft 365 Defender 入口網站 ([https://security.microsoft.com](https://security.microsoft.com)) 或從前 Microsoft Defender 資訊安全中心 () 中開啟 [https://securitycenter.windows.com](https://securitycenter.windows.com) 。 您無法使用登錄機碼、Microsoft Intune 或群組原則來啟用或停用封鎖模式中的 EDR。

## <a name="requirements-for-edr-in-block-mode"></a>封鎖模式中 EDR 的需求

| 需求  | 詳細資料  |
|---------|---------|
| 權限 | 您必須在[Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)中指派全域管理員或安全性管理員角色。 如需詳細資訊，請參閱 [基本許可權](basic-permissions.md)。 |
| 作業系統     | 裝置必須執行下列其中一個 Windows 版本： <br/>-Windows 10 (所有版本)  <br/>-Windows Server，版本1803或更新版本 <br/>-Windows Server 2019 <br/>-只有當 Microsoft Defender 防毒軟體處於主動模式時，才 Windows Server 2016 ()      |
| 適用於端點的 Microsoft Defender     | 裝置必須架至 Defender for Endpoint。 請參閱 [Microsoft Defender For Endpoint 的基本需求](minimum-requirements.md)。       |
| Microsoft Defender 防毒軟體  | 裝置必須以主動模式或被動模式安裝和執行 Microsoft Defender 防毒軟體。 [確認 Microsoft Defender 防毒軟體處於主動或被動模式](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode)。 |
| 雲端提供的保護 | 您必須設定 Microsoft Defender 防毒軟體，讓[已啟用雲端傳遞的保護](enable-cloud-protection-microsoft-defender-antivirus.md)。 |
| Microsoft Defender 防毒軟體平臺 | 裝置必須是最新的。 若要確認，使用 PowerShell，請以系統管理員身分執行 [MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) Cmdlet。 在 **AMProductVersion** 行中，您應該會看到 **4.18.2001.10** 或更新版本。 <p> 若要深入了解，請參閱[管理Microsoft Defender 防毒軟體更新及套用基準](manage-updates-baselines-microsoft-defender-antivirus.md)。 |
| Microsoft Defender 防毒軟體引擎 | 裝置必須是最新的。 若要確認，使用 PowerShell，請以系統管理員身分執行 [MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) Cmdlet。 在 **AMEngineVersion** 行中，您應該會看到 **1.1.16700.2** 或更新版本。 <p> 若要深入了解，請參閱[管理Microsoft Defender 防毒軟體更新及套用基準](manage-updates-baselines-microsoft-defender-antivirus.md)。 |

> [!IMPORTANT]
> 若要取得最佳保護值，請確定您的防病毒方案已設定為接收定期更新和基本功能，以及您的 [排除已設定](configure-exclusions-microsoft-defender-antivirus.md)。 封鎖模式中 EDR 會考慮針對 Microsoft Defender 防毒軟體定義的排除專案，但不會考慮為 Microsoft Defender for Endpoint 定義的[指示器](manage-indicators.md)。

## <a name="frequently-asked-questions"></a>常見問題集 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-if-i-have-microsoft-defender-antivirus-running-on-devices"></a>在裝置上執行 Microsoft Defender 防毒軟體時，是否需要在封鎖模式中開啟 EDR？

封鎖模式中 EDR 的主要目的是修正非 Microsoft 防病毒產品錯過的破壞後偵測。 不過，建議您將 EDR 置於封鎖模式，不論 Microsoft Defender 防毒軟體是以被動模式還是以主動模式執行。 

- 當 Microsoft Defender 防毒軟體處於被動模式時，在封鎖模式中 EDR 會提供另一層的防禦，以及 Microsoft Defender for Endpoint。 
- 當 Microsoft Defender 防毒軟體處於主動模式時，EDR 以封鎖模式不會提供額外的掃描，但可讓 Defender 在破壞後的行為中自動採取動作 EDR 偵測。

### <a name="will-edr-in-block-mode-affect-a-users-antivirus-protection"></a>會在封鎖模式中 EDR 是否會影響使用者的病毒防護？ 

在封鎖模式中 EDR 不會影響使用者裝置上執行的協力廠商防防毒保護。 如果主要防病毒解決方案未接任何問題，或發生破壞後的情況，則 EDR 以封鎖模式運作。 在封鎖模式中 EDR 的運作方式，Microsoft Defender 防毒軟體在被動模式中，但在封鎖模式中 EDR 也會封鎖和 remediates 所偵測到的惡意偽像或行為。

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>為什麼我需要讓 Microsoft Defender 防毒軟體保持最新狀態？ 

由於 Microsoft Defender 防毒軟體偵測和 remediates 惡意專案，因此務必將其保持在最新狀態。 為使封鎖模式中的 EDR 生效，它會使用最新的裝置學習模型、行為偵測和試探法。 功能 [終結點](microsoft-defender-endpoint.md) 堆疊功能的運作方式是以整合方式運作。 若要取得最佳防護值，您應該將 Microsoft Defender 防毒軟體保持最新狀態。 請參閱[管理 Microsoft Defender 防毒軟體更新及套用基準](manage-updates-baselines-microsoft-defender-antivirus.md)。 

### <a name="why-do-we-need-cloud-protection-maps-on"></a>為什麼需要 () 的雲端保護？ 

需要 Cloud protection 才能開啟裝置上的功能。 雲端防護功能可讓 [Defender For Endpoint](microsoft-defender-endpoint.md) ，根據我們的廣泛和深度安全性情報，以及行為和裝置教學模型，提供最新和最佳的保護。

### <a name="what-is-the-difference-between-active-and-passive-mode"></a>主動與被動模式之間的差異為何？

針對執行 Windows 10 的端點、Windows Server、版本1803或更新版本，或 Windows Server 2019，當 Microsoft Defender 防毒軟體處於作用中模式時，會將其當作裝置上的主要防毒軟體使用。 在被動模式中執行時，Microsoft Defender 防毒軟體不是主要的防病毒產品。 在此情況下，不會 Microsoft Defender 防毒軟體即時修正威脅。

> [!NOTE]
> 只有當裝置架至 Microsoft Defender for Endpoint 時，才可以在被動模式下執行 Microsoft Defender 防毒軟體。

如需詳細資訊，請參閱[Microsoft Defender 防毒軟體相容性](microsoft-defender-antivirus-compatibility.md)。

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>如何確認 Microsoft Defender 防毒軟體處於主動或被動模式？

若要確認 Microsoft Defender 防毒軟體是否以主動或被動模式執行，您可以在執行 Windows 的裝置上使用命令提示字元或 PowerShell。

|方法  |程序  |
|---------|---------|
| PowerShell     | 1. 選取 [[開始] 功能表]，開始輸入 `PowerShell` ，然後在結果中開啟 Windows PowerShell。 <p>2. 輸入 `Get-MpComputerStatus` 。 <p>3. 在結果清單中的 [ **AMRunningMode** ] 列中，尋找下列其中一個值： <br/>- `Normal` <br/>- `Passive Mode` <p>若要深入瞭解，請參閱 [MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus)。        |
|命令提示字元     | 1. 選取 [開始] 功能表，開始輸入 `Command Prompt` ，然後在結果中開啟 Windows 命令提示字元。 <p>2. 輸入 `sc query windefend` 。 <p>3. 在結果清單中的 [ **狀態** ] 列中，確認服務正在執行中。         |

### <a name="how-do-i-confirm-that-edr-in-block-mode-is-turned-on-with-microsoft-defender-antivirus-in-passive-mode"></a>如何確認 EDR 在封鎖模式中以被動模式 Microsoft Defender 防毒軟體開啟？

您可以使用 PowerShell，確認 EDR 在封鎖模式中已開啟，且 Microsoft Defender 防毒軟體以被動模式執行。

1. 選取 [開始] 功能表，開始輸入 `PowerShell` ，然後在結果中開啟 Windows PowerShell。 

2. 輸入 `Get-MPComputerStatus | select AMRunningMode`。

3. 確認 `EDR Block Mode` 會顯示結果。

   > [!TIP]
   > 如果 Microsoft Defender 防毒軟體以主動模式顯示，您會看到 `Normal` 而不是 `EDR Block Mode` 。 若要深入瞭解，請參閱 [MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus)。

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a>在 Windows Server 2016 上支援的封鎖模式中 EDR 嗎？

如果 Microsoft Defender 防毒軟體以主動模式或被動模式執行，則下列 Windows 版本都支援 EDR in 封鎖模式：

- 所有版本 Windows 10 () 
- Windows伺服器、版本1803或更新版本 
- Windows Server 2019 

#### <a name="what-about-windows-server-2016"></a>Windows Server 2016 的情況為何？ 

如果 Windows Server 2016 以主動模式執行 Microsoft Defender 防毒軟體，且端點架至 Defender for endpoint，則會以技術支援的封鎖模式 EDR。 不過，當 Microsoft Defender 防毒軟體不是端點上的主要防病毒方案時，在封鎖模式中 EDR 應是額外的保護。 在這種情況下，Microsoft Defender 防毒軟體會以被動模式執行。 

目前，Windows Server 2016 上不支援以被動模式執行 Microsoft Defender 防毒軟體。 若要深入瞭解，請參閱[Microsoft Defender 防毒軟體和非 Microsoft 防毒軟體/反惡意程式碼解決方案](microsoft-defender-antivirus-compatibility.md#microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions)。

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>停用封鎖模式中的 EDR 需要多少時間？

如果您選擇以封鎖模式停用 EDR，最多可能需要30分鐘的時間，系統才會停用此功能。

## <a name="see-also"></a>另請參閱

- [技術 Community 博客：在封鎖模式中引入 EDR：在其蹤跡中停止攻擊](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [行為封鎖和包含專案](behavioral-blocking-containment.md)

