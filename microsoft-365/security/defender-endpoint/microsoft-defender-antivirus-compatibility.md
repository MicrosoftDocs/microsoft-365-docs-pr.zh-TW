---
title: 與其他安全性產品的 Microsoft Defender 防病毒相容性
description: Microsoft Defender 防毒軟體如何與其他安全性產品和您所使用的作業系統進行預期。
keywords: windows defender，下一代，防毒程式，相容性，被動模式
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: tewchen, pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 8eb52e277f7987477114db9333c3f90bb581ebb5
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690096"
---
# <a name="microsoft-defender-antivirus-compatibility"></a>Microsoft Defender 防毒程式相容性

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

## <a name="overview"></a>概觀

Microsoft Defender 防毒軟體會自動啟用並安裝在執行 Windows 10 的端點和裝置上。 但是使用另一個防毒程式/反惡意程式碼解決方案時會發生什麼事？ 這取決於您是否要將 [Microsoft Defender 用於端點](microsoft-defender-endpoint.md) 搭配防防毒保護使用。
- 如果您組織的端點和裝置以非 Microsoft 防病毒/反惡意軟體方案保護，且未使用 Microsoft Defender for Endpoint，則 Microsoft Defender 防毒程式會自動進入停用模式。
- 如果您的組織使用 Microsoft Defender for Endpoint 搭配非 Microsoft 防病毒/反惡意程式碼解決方案，則 Microsoft Defender 防毒軟體會自動進入被動模式。 Microsoft Defender 防毒軟體未修正即時保護和威脅 (。 ) 
- 如果您的組織使用 Microsoft Defender for Endpoint 搭配非 Microsoft 防病毒/反惡意程式碼解決方案，而且您已 [在封鎖模式中啟用 EDR](/microsoft-365/security/defender-endpoint/edr-in-block-mode) ，則每當偵測到惡意的專案時，Microsoft Defender for Endpoint 都會採取動作來封鎖和修正專案。

## <a name="antivirus-and-microsoft-defender-for-endpoint"></a>防病毒和 Microsoft Defender for Endpoint

下表摘要說明當協力廠商防病毒產品一起使用或沒有 Microsoft Defender for Endpoint 時，Microsoft Defender 防病毒所發生的情況。 


| Windows 版本   | 反惡意程式碼保護  | Microsoft Defender for Endpoint 登記 | Microsoft Defender 防毒程式狀態     |
|------|------|-------|-------|
| Windows 10  | Microsoft 未提供或開發的協力廠商產品 | 是  | 被動模式  |
| Windows 10  | Microsoft 未提供或開發的協力廠商產品 | 否   | 自動停用模式     |
| Windows 10  | Microsoft Defender 防病毒 | 是  | 主動模式 | 
| Windows 10  | Microsoft Defender 防病毒 | 否   | 主動模式 |
| Windows Server、版本1803或更新版本，或 Windows Server 2019 | Microsoft 未提供或開發的協力廠商產品 | 是  | 必須設定為被動模式 (手動) <sup> [[1](#fn1)]<sup>  | 
| Windows Server、版本1803或更新版本，或 Windows Server 2019 | Microsoft 未提供或開發的協力廠商產品 | 否  | 必須手動停用 () <sup> [[2](#fn2)]<sup></sup>  |
| Windows Server、版本1803或更新版本，或 Windows Server 2019 | Microsoft Defender 防病毒  | 是 |         主動模式  |
| Windows Server、版本1803或更新版本，或 Windows Server 2019 | Microsoft Defender 防病毒 | 否  | 主動模式 |
| Windows Server 2016 | Microsoft Defender 防病毒 | 是 | 主動模式 |
| Windows Server 2016 | Microsoft Defender 防病毒 | 否 | 主動模式 |
| Windows Server 2016 | Microsoft 未提供或開發的協力廠商產品 | 是 | 必須手動停用 () <sup> [[2](#fn2)]<sup> |
| Windows Server 2016 | Microsoft 未提供或開發的協力廠商產品 | 否 | 必須手動停用 () <sup> [[2](#fn2)]<sup> |

 (<a id="fn1">1</a>) 在 Windows Server 上，版本1803或更新版本，或 Windows server 2019 時，當您安裝非 Microsoft 防病毒產品時，Microsoft Defender 防毒程式不會自動進入被動模式。 在這種情況下，請 [將 Microsoft Defender 防病毒功能設定為被動模式](microsoft-defender-antivirus-on-windows-server.md#need-to-set-microsoft-defender-antivirus-to-passive-mode) ，以防止在伺服器上安裝多個防病毒產品所造成的問題。

如果您使用的是 Windows Server、版本1803或更新版本，或 Windows Server 2019，您可以設定下列登錄機碼，將 Microsoft Defender 防毒軟體設定為被動模式：
- 路徑： `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- 名稱：`ForcePassiveMode`
- 類型： `REG_DWORD`
- 值：`1`

> [!NOTE]
> `ForcePassiveMode`Windows Server 2016 不支援登錄機碼。

 (<a id="fn2">2</a>) 在 Windows Server 2016 上，當您安裝非 Microsoft 防病毒產品時，Microsoft Defender 防毒程式不會自動進入被動模式。 此外，被動模式不支援 Microsoft Defender 防病毒。 在這種情況下，請 [手動停用/卸載 Microsoft Defender 防病毒](microsoft-defender-antivirus-on-windows-server.md#are-you-using-windows-server-2016) ，以防止在伺服器上安裝多個防病毒產品所造成的問題。

請參閱 [Windows server 上的 Microsoft Defender 防毒軟體](microsoft-defender-antivirus-on-windows-server.md) ，瞭解 windows server 安裝的重要差異和管理選項。

> [!IMPORTANT]
> Microsoft Defender 防病毒只適用于執行 Windows 10、Windows Server 2016、Windows Server、版本1803或更新版本的裝置，以及 Windows Server 2019。
>
> 在 Windows 8.1 和 Windows Server 2012 中，企業級端點防病毒防護是以 [System Center Endpoint protection](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10))（透過 Microsoft 端點 Configuration Manager 來管理）來提供。
>
> Windows Defender 也是針對 [windows 8.1 和 Windows Server 2012 上的消費裝置](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender)提供，但不會在 windows Server 2012 Server Core 安裝) 上提供企業層級管理 (或介面。

## <a name="functionality-and-features-available-in-each-state"></a>每種狀態中可用的功能和功能

本節中的表格摘要列出每個狀態中提供的功能和功能。 表格是專門設計為僅供參考。 它是用來說明 & 功能的功能，取決於 Microsoft Defender 防毒程式是否處於主動模式、被動模式或已停用/已停用。 

> [!IMPORTANT]
> 如果您使用的是以被動模式使用 Microsoft Defender 防病毒，或是在封鎖模式中使用 EDR，請勿關閉即時保護、雲端傳送保護或有限定期掃描等功能。 

|保護 |主動模式 |被動模式 |封鎖模式中的 EDR |停用或已卸載 |
|:---|:---|:---|:---|:---|
| [即時保護](./configure-real-time-protection-microsoft-defender-antivirus.md) 和 [雲端提供的保護](./enable-cloud-protection-microsoft-defender-antivirus.md) | 是 | 無 <sup> [[3](#fn3)]<sup> | 否 | 否 |
| [有限的定期掃描可用性](./limited-periodic-scanning-microsoft-defender-antivirus.md) | 否 | 否 | 否 | 是 |
| [檔掃描及偵測資訊](./customize-run-review-remediate-scans-microsoft-defender-antivirus.md) | 是 | 是 | 是 | 否 |
|  [威脅修正](./configure-remediation-microsoft-defender-antivirus.md) | 是 | 請參閱附注 <sup> [[4](#fn4)]<sup> | 是 | 否 |
| [安全性智慧更新](./manage-updates-baselines-microsoft-defender-antivirus.md) | 是 | 是 | 是 | 否 |

 (<a id="fn3">3</a>) 一般說來，當 Microsoft Defender 防病毒在被動模式中時，即時保護不會提供任何封鎖或強制執行，即使它已啟用並在被動模式中也是一樣。 

 (<a id="fn4">4</a>) 當 Microsoft Defender 防病毒在被動模式中時，威脅修正功能只有在排程或隨選掃描時才會啟用。

> [!NOTE]
> 當 Microsoft Defender 防病毒處於主動或被動模式時， [microsoft 365 端點資料遺失防護](/microsoft-365/compliance/endpoint-dlp-learn-about)防護會繼續正常運作。

## <a name="keep-the-following-points-in-mind"></a>請記住下列幾點

- 在 active 模式中，Microsoft Defender 防病毒是用來做為電腦上的防病毒應用程式。 將會套用設定管理員、群組原則、Intune 或其他管理產品所做的所有設定。 掃描檔案並修正威脅，並在設定工具中報告偵測資訊 (例如 Configuration Manager 或電腦本身的 Microsoft Defender 防病毒應用程式) 。

- 在被動模式中，不會使用 Microsoft Defender 防毒軟體做為防病毒應用程式，也不會透過 Microsoft Defender 防毒程式修正威脅。 會掃描檔案，並提供與 Microsoft Defender for Endpoint service 共用之威脅偵測的報告。 因此，您可能會在安全性中心主控台中遇到「Microsoft Defender 防毒程式」為來源的警示，即使 Microsoft Defender 防病毒是以被動模式。

- 在 [封鎖模式中的 EDR](/microsoft-365/security/defender-endpoint/edr-in-block-mode) 已開啟，且 Microsoft Defender 防毒程式不是主要的防病毒方案，它仍然可以偵測並修復惡意專案。

- 停用時，不會使用 Microsoft Defender 防毒軟體做為防病毒應用程式。 不會掃描檔案，也不會修正威脅。 一般不建議停用/卸載 Microsoft Defender 防病毒。如果可能的話，請在使用非 Microsoft 反惡意軟體/防病毒解決方案時，將 Microsoft Defender 防毒軟體保持在被動模式。

- 如果您是在 Microsoft Defender for Endpoint 中註冊，且使用協力廠商反惡意軟體產品，則會啟用被動模式。 [服務需要從 Microsoft Defender 防病毒服務共用一般資訊](/microsoft-365/security/defender-endpoint/defender-compatibility) ，才能正確監視裝置和網路，以進行入侵嘗試和攻擊。

- 當自動停用 Microsoft Defender 防病毒時，如果非 Microsoft 防病毒產品所提供的保護功能到期或停止提供即時防護以防範病毒、惡意程式碼或其他威脅，可自動將其重新啟用。 自動重新啟用可協助確保在您的裝置上維護防防毒保護。 它也可讓您啟用 [有限的定期掃描](limited-periodic-scanning-microsoft-defender-antivirus.md)，它會使用 Microsoft Defender 防病毒引擎定期檢查威脅，以及您的主要防病毒應用程式。

- 當 Microsoft Defender 防病毒處於被動模式時，您仍可 [管理 Microsoft Defender 防病毒的更新](manage-updates-baselines-microsoft-defender-antivirus.md);不過，如果您的裝置具有最新的非 Microsoft 防病毒產品，則無法將 Microsoft Defender 防病毒移入主動模式，以提供來自惡意程式碼的即時防護。 若要獲得最佳的安全性分層防禦和偵測 efficacy，請確定您更新 [Microsoft Defender 防防毒保護 (安全性智慧更新、引擎和平臺) ](./manage-updates-baselines-microsoft-defender-antivirus.md) （即使 Microsoft Defender 防病毒是以被動模式執行）。

   如果您卸載非 Microsoft 防病毒產品，並使用 Microsoft Defender 防毒軟體來對裝置提供保護，則 Microsoft Defender 防毒程式會自動回到其正常使用模式。

> [!WARNING]
> 請勿停用、停止或修改 Microsoft Defender 防病毒、Microsoft Defender for Endpoint 或 Windows 安全性應用程式所使用的任何相關服務。 此建議包括 *wscsvc*、 *SecurityHealthService*、 *MsSense*、 *感知*、 *WinDefend* 或 *MsMpEng* 服務和程式。 手動修改這些服務可能會造成裝置上的不穩定，而且可能使您的網路受到威脅。 停用、停止或修改這些服務時，也可能會在使用非 Microsoft 防病毒解決方案，以及其資訊在 [Windows 安全性應用程式](microsoft-defender-security-center-antivirus.md)中的顯示方式時，造成問題。


## <a name="see-also"></a>另請參閱

- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
- [Windows Server 上的 Microsoft Defender 防病毒](microsoft-defender-antivirus-on-windows-server.md)
- [封鎖模式中的 EDR](edr-in-block-mode.md)
- [設定 Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
- [解決適用於端點的 Microsoft Defender 中的誤判](defender-endpoint-false-positives-negatives.md)
- [深入瞭解 Microsoft 365 端點資料外洩防護](/microsoft-365/compliance/endpoint-dlp-learn-about)