---
title: 設定 Microsoft Defender 防病毒掃描的排除專案
description: 您可以排除檔案 (包含由 Microsoft Defender 防毒程式掃描的指定程式所修改的檔案) 和資料夾。 使用 PowerShell 驗證您的排除專案。
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.technology: mde
ms.audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 7065aa7cd1975b2f5a38e79da8618ba3efdcdac5
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275117"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a>設定及驗證 Microsoft Defender 防病毒掃描的排除專案

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

您可以從 Microsoft Defender 防病毒掃描中排除某些檔案、資料夾、處理常式及處理常式開啟的檔案。 這類排除專案適用于 [排程掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)、 [隨選掃描](run-scan-microsoft-defender-antivirus.md)，以及 [永遠開啟即時保護和監控](configure-real-time-protection-microsoft-defender-antivirus.md)。 處理常式開啟的檔案排除只適用于即時保護。

## <a name="configure-and-validate-exclusions"></a>設定及驗證排除範圍

若要設定及驗證排除，請參閱下列各項：

- 根據檔案名[、副檔名和資料夾位置，設定及驗證排除](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。 您可以根據檔案副檔名、檔案名或位置，將檔案從 Microsoft Defender 防病毒掃描中排除。

- [針對由進程開啟的檔案，設定及驗證排除](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)專案。 您可以從特定進程所開啟的掃描中排除檔案。

## <a name="recommendations-for-defining-exclusions"></a>定義排除的建議

> [!IMPORTANT]
> Microsoft Defender 防毒軟體會根據已知的作業系統行為和一般管理檔案（例如企業管理、資料庫管理及其他企業案例及案例中所使用的管理檔案），包含許多自動排除。  
> 
> 定義排除項會降低 Microsoft Defender 防毒軟體所提供的保護。 您應時刻評估與執行排除相關的風險，您應該只排除您確信不會惡意的檔案。

當您定義排除專案時，請牢記下列幾點：  

- 排除在技術上是保護缺口。 在定義排除時，一定要考慮緩解。 其他的緩解動作可能非常簡單，只要確定排除的位置具有適當的存取控制清單 (ACLs) 、審核原則，都是由最新的軟體來處理，等等。

- 定期複查排除專案。 請重新檢查並重新執行作為審查程式一部分的緩解。

- 理想狀況下，避免將排除定義為主動。 例如，請不要排除某些專案，因為您認為它可能是未來的問題。 只針對特定問題（如與符合性或應用程式相容性相關的問題）使用排除專案，以降低其效能。

- 審核排除清單變更。 安全性管理員應該保留足夠的內容，以避免為何新增特定排除。 您應該能夠提供特定原因的答案，以瞭解排除特定路徑的原因。

## <a name="related-articles"></a>相關文章

- [Windows Server 2016 上的 Microsoft Defender 防病毒排除](configure-server-exclusions-microsoft-defender-antivirus.md)
- [定義排除時應避免的常見錯誤](common-exclusion-mistakes-microsoft-defender-antivirus.md)
