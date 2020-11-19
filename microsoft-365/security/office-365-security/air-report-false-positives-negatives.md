---
title: 如何在 Microsoft Defender for Office 365 中報告自動調查的誤報或漏報
description: Microsoft Defender for Office 365 中的 AIR 是否已錯過或錯誤地偵測到什麼？ 瞭解如何將誤報或錯誤否定提交給 Microsoft 進行分析。
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
ms.date: 09/29/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: conceptual
ms.custom:
- autoir
ms.openlocfilehash: 27edc44145e7b61768d9caf00a3f308e8561d708
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357396"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>如何在自動化調查和回應功能中報告誤報/負片

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


適用於：
- 適用於 Office 365 的 Microsoft Defender

[自動調查和回應 (Office 365 中的 AIR) 功能](automated-investigation-response-office.md)是否漏掉或錯誤地偵測到某項功能？ 您可以採取一些步驟加以修正。 您可以：

- [向 Microsoft 報告誤報/負數](#report-a-false-positivenegative-to-microsoft-for-analysis)
- 視需要[調整提醒](#adjust-an-alert-to-prevent-false-positives-from-recurring) () ;和
- [復原採取的修復動作](#undo-a-remediation-action)。

使用本文做為指南。

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>將誤報報告給 Microsoft 進行分析

如果 Microsoft Defender for Office 365 中的 AIR 錯過電子郵件、電子郵件附件、電子郵件中的 URL 或 Office 檔案中的 URL，您可以 [將可疑的垃圾郵件、網路釣魚程式、URLs 和檔案提交給 Microsoft For office 365 掃描](admin-submission.md)。

您也可以 [將檔案提交給 Microsoft 以進行惡意程式碼分析](https://www.microsoft.com/wdsi/filesubmission)。

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>調整提醒以避免定期誤報

如果透過合法的使用觸發警示，或警示不准確，您可以 [在雲端 App 安全性入口網站中管理提醒](https://docs.microsoft.com/cloud-app-security/managing-alerts)。

如果您的組織使用的是 [Microsoft Defender For Endpoint](https://docs.microsoft.com/windows/security/threat-protection) ，除了 Office 365 之外，在裝置上會將檔案、IP 位址、URL 或網域視為惡意程式碼，即使它是安全的，您還是可以 [使用裝置的「允許」動作來建立自訂指示器](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)。

## <a name="undo-a-remediation-action"></a>復原修正動作

在大多數情況下，如果對電子郵件訊息、電子郵件附件或 URL 採取修正動作，而該專案實際上不是威脅，則您的安全作業小組可以復原修正動作，並採取步驟以避免定期誤報。 您可以使用 [威脅瀏覽器](#undo-an-action-using-threat-explorer) 或 [ [動作]](#undo-an-action-using-the-actions-tab-for-an-investigation) 索引標籤進行調查，以復原動作。

> [!IMPORTANT]
> 在嘗試執行下列工作之前，請先確定您具備必要的許可權。

### <a name="undo-an-action-using-threat-explorer"></a>使用威脅瀏覽器復原動作

透過威脅瀏覽器，您的安全性運作小組可以找到動作所影響的電子郵件，並可能復原動作。

****

|案例|復原選項|深入了解|
|---|---|---|
|將電子郵件路由傳送至使用者的 [垃圾郵件] 資料夾|<ul><li>將郵件移至使用者的 [刪除的郵件] 資料夾</li><li>將郵件移至使用者的收件匣</li><li>刪除郵件</li></ul>|[尋找並調查 Office 365 中傳遞的惡意電子郵件](investigate-malicious-email-that-was-delivered.md)|
|已隔離的電子郵件訊息或檔|<ul><li>發行電子郵件或檔案</li><li>刪除電子郵件或檔</li></ul>|[以系統管理員身分管理被隔離的郵件](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a>使用調查的 [動作] 索引標籤復原動作

在「行動中心」中，您可以看到已採取的修復動作，並可能復原動作。

1. 移至 [https://protection.office.com](https://protection.office.com) 並登入。 這會帶您前往安全性 & 規範中心。

2. 移至 [威脅管理]  >  [調查]。

3. 在調查清單中，選取專案識別碼旁邊的 [ **在新視窗中開啟]** 圖示。

4. 選取 [ **動作** ] 索引標籤。

5. 選取狀態為 [**已完成**] 的專案，然後在 [**決策**] 欄中尋找連結（如「**已核准**」）。 這會開啟快顯視窗，包含動作的詳細資料。

6. 若要復原動作，請選取 [ **刪除修正**]。

## <a name="related-articles"></a>相關文章

[適用於 Office 365 的 Microsoft Defender](office-365-atp.md)

[Microsoft Defender for Office 365 中的空氣](office-365-air.md)
