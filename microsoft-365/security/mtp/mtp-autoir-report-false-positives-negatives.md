---
title: 在 Microsoft 365 Defender 中處理 AIR 中的誤誤或漏報
description: MICROSOFT 365 Defender 中的 AIR 偵測到未接或錯誤？ 瞭解如何將誤誤或漏報提交至 Microsoft 進行分析。
keywords: 自動化、調查、警示、觸發、動作、補救、誤正、漏報
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 09/16/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: dbef240e28258d1ac4000c05538d0ce073a9d910
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930351"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>在自動化調查與回應功能中處理誤對/負數

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

Microsoft [](mtp-autoir.md) 365 Defender 中的自動化調查與回應功能是否遺漏或誤偵測到某些專案？ 您可以採取一些步驟來修正此問題。 您可以：

- [向 Microsoft 報告誤正/負數](#report-a-false-positivenegative-to-microsoft-for-analysis);

- [如有必要，請 (](#adjust-an-alert-to-prevent-false-positives-from-recurring) 您的) ;和 

- [復原在裝置上採取的補救動作](#undo-a-remediation-action-that-was-taken-on-a-device)。 

使用這篇文章做為指南。 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>向 Microsoft 報告誤正/負數以進行分析

|未接或偵測到錯誤的專案 |服務  |處理方式  |
|---------|---------|---------|
|- 電子郵件訊息 <br/>- 電子郵件附件 <br/>- 電子郵件訊息中的 URL<br/>- Office 檔案中的 URL      |[適用於 Office 365 的 Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[將可疑的垃圾郵件、網路釣魚、URL 和檔案提交到 Microsoft 掃描](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|裝置上的檔案或應用程式    |[適用於端點的 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection)         |[提交檔案至 Microsoft 進行惡意攻擊分析](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>調整警示以防止誤將重複出現

|案例 |服務 |處理方式 |
|--------|--------|--------|
|- 合法使用會觸發警示 <br/>- 通知不正確    |[Microsoft 雲端 App 安全性](https://docs.microsoft.com/cloud-app-security)<br/> 或 <br/>[Azure 進位威脅偵測](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[在雲端 App 安全性入口網站中管理警示](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|即使裝置是安全的，檔案、IP 位址、URL 或網域還是會被視為惡意攻擊|[適用於端點的 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection) |[建立具有「允許」動作的自訂標記](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>復原在裝置上採取的補救動作

如果在 Windows 10 裝置 (等裝置上採取補救動作) 且該專案實際上並非威脅，您的安全性作業小組可以在控制中心復原補救 [動作](mtp-action-center.md)。

> [!IMPORTANT]
> 嘗試執行 [下列工作之前](mtp-action-center.md#required-permissions-for-action-center-tasks) ，請確認您擁有必要許可權。

1. 移至 [https://security.microsoft.com](https://security.microsoft.com) 並登入。 

2. 在功能窗格中，選擇 [控制中心]。 

3. 在歷程 **記錄上** ，選取要復原的動作。 這會開啟飛出視窗。<br/>
    > [!TIP]
    > 使用篩選來縮小結果清單。 

4. 在選定專案的飛出飛出中，選取開啟 **調查頁面**。

5. 在調查詳細資料檢視中，選取動作 **按鈕** 。

6. 選取狀態為已完成 **的專案**，在決策欄中尋找連結 **，例如****已核准。** 這會開啟一個飛出視窗，包含有關動作的更多詳細資料。

7. 若要復原動作，請選取 Delete **修復**。

## <a name="see-also"></a>另請參閱

- [檢視自動調查的詳細資料和結果](mtp-autoir-results.md)
- [使用 Microsoft 365 Defender 中的進位搜尋主動搜尋威脅](advanced-hunting-overview.md)
