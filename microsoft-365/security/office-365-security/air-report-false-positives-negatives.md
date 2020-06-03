---
title: 如何在 Office 365 自動化調查和回應中報告誤報或漏報
description: Office 365 的高級威脅防護是否已錯過或錯誤地偵測到什麼？ 瞭解如何將誤報或錯誤否定提交給 Microsoft 進行分析。
keywords: 自動化，調查，警示，觸發器，動作，修正，誤報，誤報，false 負數
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 05/15/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 837232550ca392a364b9842f64a1c3f0d790a502
ms.sourcegitcommit: 33be6075fcc89d4c0a48fa7e59f3b3ebc605d9f3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2020
ms.locfileid: "44520155"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>如何在自動化調查和回應功能中報告誤報/負片

適用於：****
- Office 365 進階威脅防護

[Office 365 中的自動化調查和回應（AIR）功能](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)是否未命中或錯誤地偵測到某項功能？ 您可以採取一些步驟加以修正。 您可以：
- [向 Microsoft 報告誤報/負數](#report-a-false-positivenegative-to-microsoft-for-analysis)
- [調整提醒](#adjust-an-alert-to-prevent-false-positives-from-recurring)（如有需要）;和 
- [復原採取的修復動作](#undo-a-remediation-action)。 

使用本文做為指南。 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>將誤報報告給 Microsoft 進行分析

如果 Office 365 AIR 錯過電子郵件、電子郵件附件、電子郵件訊息中的 URL 或 Office 檔案中的 URL，您可以[將可疑的垃圾郵件、網路釣魚程式、URLs 和檔案提交給 Microsoft For office 365 掃描](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)。

您也可以[將檔案提交給 Microsoft 以進行惡意程式碼分析](https://www.microsoft.com/wdsi/filesubmission)。

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>調整提醒以避免定期誤報

如果透過合法的使用觸發警示，或警示不准確，您可以[在雲端 App 安全性入口網站中管理提醒](https://docs.microsoft.com/cloud-app-security/managing-alerts)。

如果您的組織使用的是[Microsoft Defender 高級威脅防護](https://docs.microsoft.com/windows/security/threat-protection)，除了 Office 365 之外，在裝置上也會將檔案、IP 位址、URL 或網域視為惡意程式碼，即使它是安全的，您還是可以[使用裝置的「允許」動作來建立自訂指示器](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)。

## <a name="undo-a-remediation-action"></a>復原修正動作

在大多數情況下，如果對電子郵件訊息、電子郵件附件或 URL 採取修正動作，而該專案實際上不是威脅，則您的安全作業小組可以復原修正動作，並採取步驟以避免定期誤報。 您可以使用[威脅瀏覽器](#undo-an-action-using-threat-explorer)或 [[動作]](#undo-an-action-using-the-actions-tab-for-an-investigation)索引標籤進行調查，以復原動作。 

> [!IMPORTANT]
> 在嘗試執行下列工作之前，請先確定您具備必要的許可權。

### <a name="undo-an-action-using-threat-explorer"></a>使用威脅瀏覽器復原動作

透過威脅瀏覽器，您的安全性運作小組可以找到動作所影響的電子郵件，並可能復原動作。

|案例  |復原選項  |深入了解 |
|---------|---------|---------|
|將電子郵件路由傳送至使用者的 [垃圾郵件] 資料夾     |-將郵件移至使用者的 [刪除的郵件] 資料夾<br/>-將郵件移至使用者的收件匣 <br/>-刪除郵件          |[尋找並調查 Office 365 中傳遞的惡意電子郵件](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered) |
|已隔離的電子郵件訊息或檔     |-發行電子郵件或檔案 <br/>-刪除電子郵件或檔         |[以 Office 365 系統管理員身分管理隔離的郵件和檔案](https://docs.microsoft.com/microsoft-365/security/office-365-security/manage-quarantined-messages-and-files) |


### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a>使用調查的 [動作] 索引標籤復原動作

在「行動中心」中，您可以看到已採取的修復動作，並可能復原動作。

1. 移至 [https://protection.office.com](https://protection.office.com) 並登入。 這會帶您前往安全性 & 規範中心。

2. 移至 [威脅管理]****  >  [調查]****。

3. 在調查清單中，選取專案識別碼旁邊的 [**在新視窗中開啟]** 圖示。

4. 選取 [**動作**] 索引標籤。

5. 選取狀態為 [**已完成**] 的專案，然後在 [**決策**] 欄中尋找連結（如「**已核准**」）。 這會開啟快顯視窗，包含動作的詳細資料。

6. 若要復原動作，請選取 [**刪除修正**]。

## <a name="related-articles"></a>相關文章

[Office 365 進階威脅防護](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)

[開始使用 Office 365 中的自動調查和回應（AIR）](office-365-air.md)
