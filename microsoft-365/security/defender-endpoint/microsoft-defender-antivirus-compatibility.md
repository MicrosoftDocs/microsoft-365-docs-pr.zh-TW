---
title: Microsoft Defender 防毒軟體與其他安全性產品的相容性
description: 深入瞭解與其他安全性產品及作業系統的 Microsoft Defender 防毒軟體。
keywords: windows defender，defender for endpoint，下一代，防病毒，相容性，被動模式
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: tewchen, pahuijbr
manager: dansimp
ms.technology: mde
ms.date: 07/06/2021
ms.openlocfilehash: aac84d2e957809d1c9579f25c01006798af2c0a9
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322410"
---
# <a name="microsoft-defender-antivirus-compatibility"></a>Microsoft Defender 防毒軟體相容性

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

## <a name="summary"></a>摘要

Microsoft Defender 防毒軟體會自動啟用並安裝在執行 Windows 10 的端點和裝置上。 但是當使用另一個 (非 Microsoft) 防毒軟體/反惡意軟體解決方案時，會發生什麼事？ 您可以在其他防病毒產品旁執行 Microsoft Defender 防毒軟體嗎？ 答案取決於幾個因素，例如作業系統，以及您是否要將 [Microsoft Defender 用於端點](microsoft-defender-endpoint.md) 搭配防防毒保護使用。 

## <a name="important-points-to-keep-in-mind"></a>請注意重要要點

- 在 active 模式中，Microsoft Defender 防毒軟體會當做電腦上的防病毒應用程式使用。 使用 Configuration Manager 設定的設定，將會套用群組原則、Microsoft Intune 或其他管理產品。 會掃描檔案，修正威脅，並在設定工具中報告偵測資訊 (例如設定管理員或終結點本身) 上的 Microsoft Defender 防毒軟體應用程式。

- 在被動模式中，不會將 Microsoft Defender 防毒軟體用作防病毒應用程式，且 Microsoft Defender 防毒軟體 *不* 會修正威脅。 會掃描檔案，並提供與 Microsoft Defender for Endpoint service 共用之威脅偵測的報告。 您可能會在[安全性中心](microsoft-defender-security-center.md)看到警示，顯示 Microsoft Defender 防毒軟體為來源，即使 Microsoft Defender 防毒軟體處於被動模式也是一樣。

- 當 [[封鎖模式] 中的 EDR](edr-in-block-mode.md)已開啟，且 Microsoft Defender 防毒軟體不是主要的防病毒方案時，EDR 在封鎖模式中偵測並修復在裝置上找到的惡意專案 (後的破壞性) 。 在封鎖模式中 EDR 需要以主動模式或被動模式啟用 Microsoft Defender 防毒軟體。

- 停用時，不會將 Microsoft Defender 防毒軟體用作防病毒應用程式。 不會掃描檔案，也不會修正威脅。 一般不建議停用或卸載 Microsoft Defender 防毒軟體。如果您使用非 Microsoft 反惡意程式碼/防病毒方案，請盡可能將 Microsoft Defender 防毒軟體維持在被動模式。

- 如果您是在 microsoft Defender for Endpoint 中註冊，且使用非 Microsoft 防病毒/反惡意軟體產品，則 Microsoft Defender 防毒軟體會在被動模式中啟用。 若要正確監視裝置和網路以進行入侵嘗試和攻擊，必須從 Microsoft Defender 防毒軟體中取得一般資訊，才能讓端點進行共用。 若要深入瞭解，請參閱[Microsoft Defender 防毒軟體與 Microsoft Defender for Endpoint 相容](defender-compatibility.md)。 

- 當 Microsoft Defender 防毒軟體處於被動模式時，您仍可[管理 Microsoft Defender 防毒軟體的更新](manage-updates-baselines-microsoft-defender-antivirus.md);不過，如果您的裝置具有非 Microsoft 防病毒產品，且該產品提供來自惡意程式碼的即時防護，您就無法將 Microsoft Defender 防毒軟體移入主動模式。 若要獲得最佳的安全性分層防禦和偵測 efficacy，請務必取得您的防病毒和 antimwalware 更新，即使 Microsoft Defender 防毒軟體是以被動模式執行。 請參閱[管理 Microsoft Defender 防毒軟體更新及套用基準](manage-updates-baselines-microsoft-defender-antivirus.md)。

- 當自動停用 Microsoft Defender 防毒軟體時，如果非 Microsoft 防病毒/反惡意軟體產品到期，則可以自動重新啟用它，否則會停止提供即時防護病毒、惡意程式碼或其他威脅。 自動重新啟用 Microsoft Defender 防毒軟體可協助確保您的端點維護防防毒保護。 您也可以啟用[有限的定期掃描](limited-periodic-scanning-microsoft-defender-antivirus.md)，當您使用非 Microsoft 防病毒應用程式時，使用 Microsoft Defender 防毒軟體引擎定期檢查威脅。

## <a name="microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions"></a>Microsoft Defender 防毒軟體和非 Microsoft 防毒軟體/反惡意軟體解決方案

作業系統、防病毒產品及 Defender for Endpoint 會影響 Microsoft Defender 防毒軟體為主動模式、被動模式或已停用。 下表摘要說明當非 microsoft 防毒軟體/反惡意程式碼一起使用或沒有 microsoft Defender for Endpoint 時，Microsoft Defender 防毒軟體會發生什麼事。 

| Windows 版本   | 防病毒/反惡意程式碼解決方案  | 架至 <br/> Endpoint 的 Defender？ | Microsoft Defender 防毒軟體狀態     |
|------|------|-------|-------|
| Windows 10  | Microsoft Defender 防毒軟體 | 是  | 主動模式 | 
| Windows 10  | Microsoft Defender 防毒軟體 | 否   | 主動模式 |
| Windows 10  | 非 Microsoft 防病毒/反惡意程式碼解決方案 | 是  | 被動模式 (會自動)  |
| Windows 10  | 非 Microsoft 防病毒/反惡意程式碼解決方案 | 否   | 停用模式 (會自動)     |
| Windows伺服器、版本1803或更新版本 <p> Windows Server 2019 | Microsoft Defender 防毒軟體  | 是 |         主動模式  |
| Windows伺服器、版本1803或更新版本 <p> Windows Server 2019 | Microsoft Defender 防毒軟體 | 否  | 主動模式 |
| Windows伺服器、版本1803或更新版本 <p> Windows Server 2019 | 非 Microsoft 防病毒/反惡意程式碼解決方案 | 是  | Microsoft Defender 防毒軟體必須設定為被動模式 (手動) <sup> [[1](#fn1)]<sup>  | 
| Windows伺服器、版本1803或更新版本 <p> Windows Server 2019 | 非 Microsoft 防病毒/反惡意程式碼解決方案 | 否  | 必須 (手動停用 Microsoft Defender 防毒軟體) <sup> [[2](#fn2)]<sup></sup>  |
| Windows Server 2016 | Microsoft Defender 防毒軟體 | 是 | 主動模式 |
| Windows Server 2016 | Microsoft Defender 防毒軟體 | 否 | 主動模式 |
| Windows Server 2016 | 非 Microsoft 防病毒/反惡意程式碼解決方案 | 是 | 必須 (手動停用 Microsoft Defender 防毒軟體) <sup> [[2](#fn2)]<sup> |
| Windows Server 2016 | 非 Microsoft 防病毒/反惡意程式碼解決方案 | 否 | 必須 (手動停用 Microsoft Defender 防毒軟體) <sup> [[2](#fn2)]<sup> |

 (<a id="fn1">1</a>) 在 Windows Server 上，版本1803或更新版本，或是 Windows Server 2019，Microsoft Defender 防毒軟體當您安裝非 Microsoft 防病毒產品時，不會自動進入被動模式。 在這種情況下，[將 Microsoft Defender 防毒軟體設定為被動式模式](microsoft-defender-antivirus-on-windows-server.md#need-to-set-microsoft-defender-antivirus-to-passive-mode)，以防止在伺服器上安裝多個防病毒產品所造成的問題。 您可以使用 PowerShell、群組原則或登錄機碼，將 Microsoft Defender 防毒軟體設定為被動模式。

如果您使用 Windows Server、版本1803或更新版本，或是 Windows Server 2019，您可以設定下列登錄機碼，將 Microsoft Defender 防毒軟體設定為被動式模式：
- 路徑： `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- 名稱：`ForceDefenderPassiveMode`
- 類型： `REG_DWORD`
- 值：`1`

> [!NOTE]
> Windows Server 2016 不支援被動模式。 `ForceDefenderPassiveMode`登錄機碼可用於 Windows Server、版本1803或更新版本，或 Windows 伺服器2019，但不能 Windows Server 2016。 

 (<a id="fn2">2</a>) 在 Windows Server 2016 上，如果您使用非 Microsoft 防病毒產品，您就無法在被動模式或主動模式中執行 Microsoft Defender 防毒軟體。 在這種情況下，請[手動停用/卸載 Microsoft Defender 防毒軟體](microsoft-defender-antivirus-on-windows-server.md#are-you-using-windows-server-2016)，以防止在伺服器上安裝多個防病毒產品所造成的問題。

請參閱[Windows server 上的 Microsoft Defender 防毒軟體](microsoft-defender-antivirus-on-windows-server.md)，以瞭解 Windows 伺服器安裝的主要差異和管理選項。

> [!IMPORTANT]
> Microsoft Defender 防毒軟體只能在執行 Windows 10、Windows Server 2016、Windows 伺服器、版本1803或更新版本的裝置上使用，以及 Windows Server 2019。
>
> 在 Windows 8.1 和 Windows Server 2012 中，企業級端點防病毒防護是以[System Center Endpoint Protection](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10))（透過 Microsoft Endpoint Configuration Manager 管理）來提供。
>
> Windows Defender 也是針對[Windows 8.1 和 Windows Server 2012 上的消費裝置](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender)提供，但是不會提供企業層級的管理 (或 Windows Server 2012 Server 核心安裝) 上的介面。

## <a name="how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality"></a>Microsoft Defender 防毒軟體如何影響 Defender for Endpoint 功能

本節中的表格摘要列出每個狀態中提供的功能和功能。 表格是專門設計為僅供參考。 其主要目的在於說明 Microsoft Defender 防毒軟體是否是作用中的模式、被動模式或已停用或已停用的 & 功能。 

> [!IMPORTANT]
> 如果您是以被動模式使用 Microsoft Defender 防毒軟體，或是在封鎖模式中使用 EDR，請勿關閉即時保護、雲端提供的保護或有限的定期掃描功能。 

|保護 |主動模式 |被動模式 |封鎖模式中的 EDR |停用或已卸載 |
|:---|:---|:---|:---|:---|
| [即時保護](configure-real-time-protection-microsoft-defender-antivirus.md) 和 [雲端提供的保護](enable-cloud-protection-microsoft-defender-antivirus.md) | 是 | 無 <sup> [[3](#fn3)]<sup> | 否 | 否 |
| [有限的定期掃描可用性](limited-periodic-scanning-microsoft-defender-antivirus.md) | 否 | 否 | 否 | 是 |
| [檔掃描及偵測資訊](customize-run-review-remediate-scans-microsoft-defender-antivirus.md) | 是 | 是 | 是 | 否 |
|  [威脅修正](configure-remediation-microsoft-defender-antivirus.md) | 是 | 請參閱附注 <sup> [[4](#fn4)]<sup> | 是 | 否 |
| [安全性智慧更新](manage-updates-baselines-microsoft-defender-antivirus.md) | 是 | 是 | 是 | 否 |

 (<a id="fn3">3</a>) 一般說來，當 Microsoft Defender 防毒軟體處於被動模式時，即時保護不會提供任何封鎖或強制執行，即使它已啟用並在被動模式中也是一樣。 

 (<a id="fn4">4</a>) 當 Microsoft Defender 防毒軟體處於被動模式時，威脅修復功能只有在排程或隨選掃描時才會使用。

> [!NOTE]
> 當 Microsoft Defender 防毒軟體處於主動或被動模式時， [Microsoft 365 端點資料遺失防護](/microsoft-365/compliance/endpoint-dlp-learn-about)防護會繼續正常運作。

## <a name="why-defender-for-endpoint-matters"></a>為何要將 Defender 用於端點的重要事項

即使您使用非 Microsoft 防病毒/反惡意程式碼解決方案，也請考慮將端點上架至 [Defender]。 在大多數情況下，當您將裝置上架到 Defender for Endpoint 時，您可以使用 Microsoft Defender 防毒軟體與非 Microsoft 防病毒解決方案搭配使用，以新增保護功能。 例如，您可以[在封鎖模式中使用 EDR](edr-in-block-mode.md)，它會封鎖和 remediates 您的主要防病毒解決方案可能錯過的惡意專案。 

以下為運作方式：

- 如果您組織的用戶端裝置受到非 Microsoft 防病毒/antimwalware 解決方案的保護，當這些裝置架至 Defender for Endpoint 時，Microsoft Defender 防毒軟體會自動進入被動模式。 在此情況下，會發生威脅偵測，但 Microsoft Defender 防毒軟體未修正即時保護和威脅。
   
   > [!NOTE]
   > 這種特殊案例不適用於執行 Windows Server 的端點。

- 如果您組織的用戶端裝置受到非 Microsoft 防病毒/反惡意程式碼解決方案保護，且這些裝置不會架至 Microsoft Defender for Endpoint，則 Microsoft Defender 防毒軟體會自動進入停用模式。 在此情況下，Microsoft Defender 防毒軟體不會偵測或修正威脅。
   
   > [!NOTE]
   > 這種特殊案例不適用於執行 Windows Server 的端點。

- 如果組織的端點執行 Windows Server，而這些端點是由非 Microsoft 防毒程式/反惡意程式碼解決方案所保護，當這些端點架至 Defender for Endpoint 時，Microsoft Defender 防毒軟體不會自動進入被動模式或停用模式。 在此特殊案例中，您必須適當地設定 Windows 伺服器端點。 

   - 在 Windows server 上，版本1803或更新版本，以及 Windows 伺服器2019，您可以將 Microsoft Defender 防毒軟體設定為以被動模式執行。 
   - 在 Windows Server 2016 上，Microsoft Defender 防毒軟體必須停用 (Windows Server 2016) 不支援被動式模式。

- 如果您組織的端點受到非 Microsoft 防病毒/反惡意軟體解決方案的保護，當這些裝置在啟用[封鎖模式 EDR](/microsoft-365/security/defender-endpoint/edr-in-block-mode)的情況下架至 Defender 時，則會將 defender 用於端點區塊和 remediates 惡意的偽像。
   
   > [!NOTE]
   > 此特定案例不適用於 Windows Server 2016。 在封鎖模式中 EDR 需要以主動模式或被動模式啟用 Microsoft Defender 防毒軟體。


> [!WARNING]
> 請勿停用、停止或修改 Microsoft Defender 防毒軟體、Microsoft Defender for Endpoint 或 Windows 安全性應用程式所使用的任何相關服務。 此建議包括 *wscsvc*、 *SecurityHealthService*、 *MsSense*、 *感知*、 *WinDefend* 或 *MsMpEng* 服務和程式。 手動修改這些服務可能會造成裝置上的不穩定，而且可能使您的網路受到威脅。 停用、停止或修改這些服務時，也可能會在使用非 Microsoft 防病毒解決方案，以及其資訊在[Windows 安全性應用程式](microsoft-defender-security-center-antivirus.md)中的顯示方式時造成問題。


## <a name="see-also"></a>另請參閱

- [Windows 10 中的 Microsoft Defender 防毒軟體](microsoft-defender-antivirus-in-windows-10.md)
- [Windows Server 上的 Microsoft Defender 防毒軟體](microsoft-defender-antivirus-on-windows-server.md)
- [封鎖模式中的 EDR](edr-in-block-mode.md)
- [設定 Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
- [解決適用於端點的 Microsoft Defender 中的誤判/漏報](defender-endpoint-false-positives-negatives.md)
- [深入瞭解 Microsoft 365 端點資料外洩防護](/microsoft-365/compliance/endpoint-dlp-learn-about)
