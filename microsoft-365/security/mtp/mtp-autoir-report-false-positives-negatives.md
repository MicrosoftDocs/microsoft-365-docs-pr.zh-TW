---
title: 如何報告誤判或漏報中產生 Microsoft 威脅防護中
description: 某個項目已未接或錯誤偵測到的空調中 Microsoft 威脅防護？ 了解如何提交誤判或 false 的負號給 Microsoft 進行分析。
keywords: 自動化，調查、 提醒、 觸發程序、 動作、 修復、 正數，則為 false 誤判
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 01/29/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 1177f552652e728928a2b1d322b4ce0217415509
ms.sourcegitcommit: ca2209d9176f99048d0a7adc20261029ca23dcbd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2020
ms.locfileid: "41774189"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>如何報告中自動進行調查並回應功能，則為 false positive/負號

適用於：****
- Microsoft 威脅防護

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

未[自動的調查及回應功能](mtp-autoir.md)Microsoft 威脅防護中遺漏或錯誤偵測到某個嗎？ 有修正此問題時可採取的步驟。 您可以：
- [報告可為正數/誤判給 Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis)。
- [調整您的通知](#adjust-an-alert-to-prevent-false-positives-from-recurring)（如果需要）;和 
- [復原，拍攝裝置的修復動作](#undo-a-remediation-action-that-was-taken-on-a-device)。 

使用本文做為指南。 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>向 Microsoft 報告可為正數/誤判進行分析

|未接或錯誤偵測到的項目 |Service  |處理方式  |
|---------|---------|---------|
|電子郵件訊息 <br/>電子郵件附件 <br/>-在 [電子郵件 URL<br/>-在 Office 檔案 URL      |[Office 365 進階威脅防護](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[送出可疑的垃圾郵件、 釣魚程式、 Url 和 microsoft Office 365 掃描的檔案](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|檔案或裝置上的應用程式    |[Windows Defender 進階威脅防護](https://docs.microsoft.com/windows/security/threat-protection)         |[提交給 Microsoft 進行惡意程式碼分析的檔案](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>調整以避免誤判週期性警示

|案例 |Service |處理方式 |
|--------|--------|--------|
|-合法的使用時觸發警示 <br/>-警示是不正確    |[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)<br/> 或 <br/>[Azure 的進階的威脅偵測](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[管理提醒在 Cloud App Security 入口網站](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|檔案、 IP 地址、 URL 或網域會被視為惡意程式碼在裝置上，即使其為安全|[Windows Defender 進階威脅防護](https://docs.microsoft.com/windows/security/threat-protection) |[使用 「 允許 「 巨集指令建立的自訂標記](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>復原裝置上的修復動作

如果補救動作 （例如 Windows 10 裝置） 裝置上，且實際上全新的項目，您的安全性作業小組可以復原[重要訊息中心](mtp-action-center.md)中的補救動作。

> [!IMPORTANT]
> 確定您嘗試執行下列工作之前，先具有[必要權限](mtp-action-center.md#required-permissions-for-action-center-tasks)。

1. 移至 [https://security.microsoft.com](https://security.microsoft.com) 並登入。 

2. 在功能窗格中，選擇 [控制中心]****。 

3. 在 [**歷程記錄**] 索引標籤中，選取您想要復原的動作。 如此會開啟彈出式視窗。<br/>
    > [!TIP]
    > 使用篩選來縮小結果清單中。 

4. 在彈出式視窗中選取的項目，選取 [**開啟調查] 頁面**。

5. 在調查詳細資料] 檢視中，選取 [**動作**] 索引標籤。

6. 選取項目具有狀態為 **[已完成**，並尋找中的連結，例如**已核准**，**決定**資料行。 這會開啟巨集指令的更多詳細彈出式視窗。

7. 若要復原的動作，請選取 [**刪除修復**]。

## <a name="related-articles"></a>相關文章

- [與自動化調查及回應相關的核准或拒絕動作](mtp-autoir-actions.md)
- [深入了解重要訊息中心](mtp-action-center.md)
- [使用 Microsoft 威脅防護中的進階搜捕功能主動尋找威脅](advanced-hunting-overview.md)
