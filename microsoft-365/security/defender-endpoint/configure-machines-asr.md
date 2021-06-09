---
title: 優化 ASR 規則的部署和偵測
description: 優化攻擊面減少 (ASR) 規則可識別及避免一般惡意程式碼利用漏洞。
keywords: 板載，Intune management，microsoft defender for Endpoint，microsoft defender，Windows Defender，攻擊面降低，ASR，安全性基準
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a5590e62e7838bb9f611320b6d0e5c573b2be084
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841555"
---
# <a name="optimize-asr-rule-deployment-and-detections"></a>優化 ASR 規則的部署和偵測

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [註冊免費試用版](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)。

[攻擊面減少 (ASR) 規則](./attack-surface-reduction.md) 會識別及避免一般惡意程式碼利用漏洞。 它們會控制可能的惡意程式碼的執行時機和方式。 例如，他們可以阻止 JavaScript 或 VBScript 啟動已下載的可執行檔、從 Office 宏封鎖 WIN32 API 呼叫，以及從 USB 磁片磁碟機封鎖執行的程式。

![攻擊面管理卡](images/secconmgmt_asr_card.png)<br>
*攻擊面管理卡*

「*攻擊面管理卡*」是 Microsoft 365 安全性中心工具的進入點，可供您用來進行下列作業：

* 瞭解目前如何在組織中部署 ASR 規則。
* 檢查 ASR 偵測並找出可能不正確的偵測結果。
* 分析排除專案的影響，並產生要排除的檔案路徑清單。

選取 [**移至攻擊介面管理**  >  **監控] & 報告 > 攻擊面減少規則，> 新增排除** 專案。 您可以從那裡流覽至 Microsoft 365 安全性中心的其他區段。

![Microsoft 365 security center 中的攻擊面降低規則頁面上新增排除標籤](images/secconmgmt_asr_m365exlusions.png)<br>
*Microsoft 365 安全性中心的攻擊面降低規則頁面中的 [**新增排除**] 索引標籤*

> [!NOTE]
> 若要存取 Microsoft 365 的安全性中心，您需要 Microsoft 365 E3 或 E5 授權，以及 Azure Active Directory 上具有特定角色的帳戶。 [讀取必要的授權和許可權](/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions)。

如需 Microsoft 365 安全性中心內 ASR 規則部署的詳細資訊，請參閱[監視和管理 ASR 規則部署和](/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections)偵測。

**相關主題**

* [確保您的裝置已正確設定](configure-machines.md)
* [取得架至 Microsoft Defender for Endpoint 的裝置](configure-machines-onboarding.md)
* [監視 Microsoft Defender for Endpoint security 基準的合規性](configure-machines-security-baseline.md)
