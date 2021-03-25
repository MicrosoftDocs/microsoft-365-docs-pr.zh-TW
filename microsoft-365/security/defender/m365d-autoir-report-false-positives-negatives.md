---
title: 在 Microsoft 365 Defender 中處理空氣中的誤報或漏報
description: Microsoft 365 Defender 中的 AIR 是否已錯過或錯誤地偵測到什麼？ 瞭解如何將誤報或錯誤否定提交給 Microsoft 進行分析。
keywords: 自動化，調查，警示，修正，誤報，false 負數
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 01/29/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 851fd05f0fec4b8d113e515783092eed0114db0f
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199110"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>在自動化調查和回應功能中處理誤報/負片

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用於：**
- Microsoft 365 Defender

任何威脅防護解決方案都會偶爾發生誤報/負片錯誤。 如果 Microsoft 365 Defender 中的 [自動調查和回應功能](m365d-autoir.md) 未接或錯誤地偵測到某項，則您的安全作業小組可以採取下列步驟：

- [向 Microsoft 報告誤報/負數](#report-a-false-positivenegative-to-microsoft-for-analysis)
- 視需要[調整提醒](#adjust-an-alert-to-prevent-false-positives-from-recurring) () ;和 
- [復原對裝置採取的修正動作](#undo-a-remediation-action-that-was-taken-on-a-device)。 

下列各節說明如何執行這些工作。

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>將誤報報告給 Microsoft 進行分析

|偵測到未接或誤接專案 |服務  |處理方式  |
|---------|---------|---------|
|-電子郵件 <br/>-電子郵件附件 <br/>-電子郵件訊息中的 URL<br/>-Office 檔案中的 URL      |[適用於 Office 365 的 Microsoft Defender](/microsoft-365/security/office-365-security/defender-for-office-365)        |[將可疑的垃圾郵件、網路釣魚、URLs 及檔案提交給 Microsoft 進行掃描](../office-365-security/admin-submission.md)         |
|裝置上的檔或應用程式    |[適用於端點的 Microsoft Defender](/windows/security/threat-protection)         |[將檔案提交給 Microsoft 以進行惡意程式碼分析](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>調整提醒以避免定期誤報

|案例 |服務 |處理方式 |
|--------|--------|--------|
|-由合法使用所觸發的警示 <br/>-警示不准確    |[Microsoft Cloud App Security](/cloud-app-security)<br/> 或 <br/>[Azure 高級威脅偵測](/azure/security/fundamentals/threat-detection)         |[在雲端應用程式安全性入口網站中管理提醒](/cloud-app-security/managing-alerts)         |
|檔案、IP 位址、URL 或網域在裝置上視為惡意程式碼，即使它是安全的|[適用於端點的 Microsoft Defender](/windows/security/threat-protection) |[使用 "Allow" 動作建立自訂指示器](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |

## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>復原裝置上所執行的修復動作

如果對實體 (採取修正動作，例如裝置或電子郵件訊息) ，且受影響的實體實際上不是威脅，您的安全性作業小組可以復原「 [行動中心](m365d-action-center.md)」中的修復動作。

1. 移至 [https://security.microsoft.com](https://security.microsoft.com) 並登入。 
2. 在功能窗格中，選擇 [控制中心]。 
3. 在 [ **記錄** ] 索引標籤上，選取您要復原的動作。 其快顯視窗隨即開啟。
4. 在快顯視窗中，選取 [ **復原**]。

> [!TIP]
> 請參閱 [復原已完成動作](m365d-autoir-actions.md#undo-completed-actions)。

## <a name="see-also"></a>另請參閱

- [檢視自動調查的詳細資料和結果](m365d-autoir-results.md)
- [使用 Microsoft 365 Defender 中的高級搜尋主動搜尋威脅](advanced-hunting-overview.md)
- [在 Microsoft Defender for Endpoint 中處理誤報/負片](/windows/security/threat-protection/microsoft-defender-atp/defender-endpoint-false-positives-negatives)