---
title: 設定 Microsoft Defender AV 設定的本機覆寫
description: 在 Microsoft Defender AV 中，啟用或停用使用者在本機變更設定。
keywords: 本機覆寫、本機原則、群組原則、gpo、鎖定、合併、清單
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 02/13/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4a35c6717fd7a1834364df32cf5570c83a5b776e
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274517"
---
# <a name="prevent-or-allow-users-to-locally-modify-microsoft-defender-antivirus-policy-settings"></a>防止或允許使用者本機修改 Microsoft Defender 防毒軟體原則設定

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

根據預設，透過「群組原則」物件部署到網路端點的 Microsoft Defender 防毒軟體設定，可防止使用者在本機上變更設定。 在某些情況中，您可以變更這種情況。

例如，您可能需要允許某些使用者群組 (例如，安全性調查人員和威脅調查人員) 對使用的端點上的個別設定進行進一步的控制。

## <a name="configure-local-overrides-for-microsoft-defender-antivirus-settings"></a>設定 Microsoft Defender 防毒軟體設定的本機覆寫

這些原則的預設設定為 [ **停用**]。

如果設定為 [**啟用**]，端點上的使用者可以使用 [Windows 安全性](microsoft-defender-security-center-antivirus.md)app、本機組策略設定，以及適當)  (中的 PowerShell Cmdlet，對相關聯的設定進行變更。

下表列出每個覆寫原則設定，以及相關聯的功能或設定的設定指示。

若要設定這些設定：

1. 在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。

2. 在 [**群組原則管理編輯器**] 移至 [電腦設定]，然後按一下 [**系統****管理範本**]。

3. 展開樹狀目錄， **Windows 元件 > Microsoft Defender 防毒軟體**，然後在下表中所指定的 **位置**。

4. 按兩下下表中所指定的原則 **設定** ，並將選項設定為您想要的設定。 按一下 **[確定]**，然後對任何其他設定重複此步驟。

5. 照常部署群組原則物件。

位置 | 設定 | 文章
---|---|---|---
地圖 | 設定本地設定覆寫以進行 Microsoft MAPS 報告 | [啟用雲端傳送保護](enable-cloud-protection-microsoft-defender-antivirus.md)
隔離 | 設定從隔離區移除專案的本機設定覆寫 | [設定掃描的修正](configure-remediation-microsoft-defender-antivirus.md)
即時保護 | 設定本機設定覆寫以監控電腦上的檔案和程式活動 | [啟用和設定 Microsoft Defender 防毒軟體 always on 防護和監控](configure-real-time-protection-microsoft-defender-antivirus.md)
即時保護 | 設定針對內送和外寄檔案活動進行監視的本機設定覆寫 | [啟用和設定 Microsoft Defender 防毒軟體 always on 防護和監控](configure-real-time-protection-microsoft-defender-antivirus.md)
即時保護 | 設定本機設定覆寫以掃描所有已下載的檔案和附件 | [啟用和設定 Microsoft Defender 防毒軟體 always on 防護和監控](configure-real-time-protection-microsoft-defender-antivirus.md)
即時保護 | 設定本機設定超越開啟行為監控 | [啟用和設定 Microsoft Defender 防毒軟體 always on 防護和監控](configure-real-time-protection-microsoft-defender-antivirus.md)
即時保護 | 設定本機設定覆寫以開啟即時保護 | [啟用和設定 Microsoft Defender 防毒軟體 always on 防護和監控](configure-real-time-protection-microsoft-defender-antivirus.md)
修復 | 設定本機設定覆寫以執行排定的完整掃描以完成修復的時間 | [設定掃描的修正](configure-remediation-microsoft-defender-antivirus.md)
掃描 | 設定本機設定覆寫以取得 CPU 使用率的最大百分比 | [設定及執行掃描](run-scan-microsoft-defender-antivirus.md)
掃描 | 設定排程掃描日的本機設定覆寫 | [設定排程掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
掃描 | 設定計劃快速掃描時間的本機設定覆寫 | [設定排程掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
掃描 | 設定計劃掃描時間的本機設定覆寫 | [設定排程掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
掃描 | 設定針對掃描類型用於排程掃描的本機設定覆寫 | [設定排程掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)

<a id="merge-lists"></a>

## <a name="configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged"></a>設定如何合併本機和全域定義的威脅修復和排除清單

您也可以設定如何組合或合併本機定義的清單與全域定義的清單。 此設定適用于 [排除清單](configure-exclusions-microsoft-defender-antivirus.md)、 [指定的修正清單](configure-remediation-microsoft-defender-antivirus.md)和 [攻擊面降低](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)。

依預設，已在本機組策略中設定的清單和 Windows 安全性應用程式會與您在網路上部署的適當群組原則物件所定義的清單合併。 在發生衝突的情況下，全域定義的清單優先。

您可以停用此設定，以確保只會使用全域定義的清單 (例如任何已部署的 Gpo) 中的清單。

### <a name="use-group-policy-to-disable-local-list-merging"></a>使用群組原則來停用本地清單合併

1. 在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。

2. 在 [**群組原則管理編輯器**] 移至 [電腦設定]，然後按一下 [**系統****管理範本**]。

3. 展開樹狀目錄，以 **Windows 元件 > Microsoft Defender 防毒軟體**。

4. 按兩下 [ **設定清單的本機系統管理員合併行為** ]，並將選項設定為 [ **已停用**]。 按一下 ****[確定]。

> [!NOTE]
> 如果您停用本機清單合併，它會覆寫控制的資料夾存取設定。 它也會覆寫任何受保護的資料夾或本機系統管理員所設定的允許應用程式。 如需受控資料夾存取設定的詳細資訊，請參閱[在 Windows 安全性中允許封鎖的應用程式](https://support.microsoft.com/help/4046851/windows-10-allow-blocked-app-windows-security)。

## <a name="related-topics"></a>相關主題

- [Windows 10 中的 Microsoft Defender 防毒軟體](microsoft-defender-antivirus-in-windows-10.md)
- [設定使用者與 Microsoft Defender 防毒軟體互動互動](configure-end-user-interaction-microsoft-defender-antivirus.md)