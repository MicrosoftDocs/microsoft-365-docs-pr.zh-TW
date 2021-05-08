---
title: 如何在 Microsoft Defender 中對 Office 365 進行自動調查時報告誤報或漏報
description: Office 365 中的無線 AIR 是否已錯過或錯誤地偵測到什麼專案？ 瞭解如何將誤報或錯誤否定提交給 Microsoft 進行分析。
keywords: 自動化，調查，警示，觸發器，動作，修正，誤報，誤報，false 負數
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
ms.prod: m365-security
ms.date: 01/29/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: how-to
ms.custom:
- autoir
ms.technology: mdo
ms.openlocfilehash: 036ef1c97788f310c5b906ae5f80076ca2359cdb
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275081"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>如何在自動化調查和回應功能中報告誤報/負片

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [適用於 Office 365 的 Microsoft Defender 方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

如果[自動調查和回應 (Office 365](automated-investigation-response-office.md)未接或誤偵測某專案的空氣) 功能，您的安全性運作小組可以採取這些步驟加以修正。 這類動作包括：

- [向 Microsoft 報告誤報/負數](#report-a-false-positivenegative-to-microsoft-for-analysis)
- 在需要時[調整提醒](#adjust-an-alert-to-prevent-false-positives-from-recurring) () ;和
- 復原[採取的修復動作](#undo-a-remediation-action)。

使用本文做為指南。

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>將誤報報告給 Microsoft 進行分析

如果 Microsoft Defender 中的 AIR Office 365 錯過電子郵件、電子郵件附件、電子郵件訊息中的 url 或 Office 檔案中的 url，您可以[將可疑的垃圾郵件、網路釣魚程式、URLs 和檔案提交至 Microsoft，以進行 Office 365 掃描](admin-submission.md)。

您也可以 [將檔案提交給 Microsoft 以進行惡意程式碼分析](https://www.microsoft.com/wdsi/filesubmission)。

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>調整提醒以避免定期誤報

如果合法的使用會觸發警示，或警示不准確，您可以[在雲端 App 安全性入口網站中管理提醒](/cloud-app-security/managing-alerts)。

如果您的組織使用的是[Microsoft Defender for Endpoint](/windows/security/threat-protection) ，除了 Office 365 之外，在裝置上也會將檔案、IP 位址、URL 或網域視為惡意程式碼，即使它是安全的，您還是可以[使用裝置的「允許」動作來建立自訂指示器](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)。

## <a name="undo-a-remediation-action"></a>復原修正動作

在大多數情況下，如果對電子郵件訊息、電子郵件附件或 URL 採取修正動作，而該專案實際上不是威脅，則您的安全作業小組可以復原修正動作，並採取步驟以避免定期誤報。 您可以使用 [威脅瀏覽器](#undo-an-action-using-threat-explorer) 或 [ [動作]](#undo-an-action-in-the-action-center) 索引標籤進行調查，以復原動作。

> [!IMPORTANT]
> 在嘗試執行下列工作之前，請先確定您具備必要的許可權。

### <a name="undo-an-action-using-threat-explorer"></a>使用威脅瀏覽器復原動作

透過威脅瀏覽器，您的安全性運作小組可以找到動作所影響的電子郵件，並可能復原動作。

|案例|復原選項|深入了解|
|---|---|---|
|將電子郵件路由傳送至使用者的 [垃圾郵件] 資料夾|-將郵件移至使用者的 [刪除的郵件] 資料夾<br/>-將郵件移至使用者的收件匣<br/>-刪除郵件|[尋找並調查 Office 365 中傳遞的惡意電子郵件](investigate-malicious-email-that-was-delivered.md)|
|已隔離的電子郵件訊息或檔|-發行電子郵件或檔案<br/>-刪除電子郵件或檔|[以系統管理員身分管理被隔離的郵件](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a>復原動作中心的動作

在「行動中心」中，您可以看到已採取的修復動作，並可能復原動作。

1. 請移至 Microsoft 365 的安全性中心 (<https://security.microsoft.com>) 。
2. 在功能窗格中，選取 [ **動作中心**]。
3. 選取 [ **記錄** ] 索引標籤，以查看已完成的動作清單。
4. 選取專案。 其快顯視窗隨即開啟。
5. 在快顯視窗中，選取 [ **復原**]。  (只有可復原的動作才能具有 [ **復原** ] 按鈕。 ) 

## <a name="see-also"></a>另請參閱

- [適用於 Office 365 的 Microsoft Defender](defender-for-office-365.md)
- [Microsoft Defender Office 365 中的自動化調查](office-365-air.md)
