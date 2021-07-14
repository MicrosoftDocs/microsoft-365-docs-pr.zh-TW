---
title: 開始使用應用程式威脅偵測和補救
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 開始使用應用程式威脅偵測和補救。
ms.openlocfilehash: 6229d2cf94ec1ba892929f399fe49cf88da608d1
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420078"
---
# <a name="get-started-with-app-threat-detection-and-remediation"></a>開始使用應用程式威脅偵測和補救

>*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*

Microsoft 應用程式控管會收集內建應用程式控管偵測方法根據惡意應用程式活動所產生的威脅警示，以及您建立之作用中應用程式原則所產生的原則型警示。

第一個檢視應用程式警示的地方是位於 [https://compliance.microsoft.com/appgovernance](https://compliance.microsoft.com/appgovernance) 的應用程式控管儀表板。

![Microsoft 365 合規性中心的應用程式控管概觀頁面，且已醒目提示偵測和原則警示區段](..\media\manage-app-protection-governance\mapg-cc-overview-alerts.png)

在此概觀頁面上，**偵測和原則警示** 區段會列出最新的警示。 您可以使用此區段快速查看租用戶目前的應用程式警示活動。

若要查看所有警示，請選取 [警示] 索引標籤。

## <a name="whats-available-on-the-alerts-page"></a>[警示] 頁面上提供的資訊

[警示] 會列出您租用戶的所有應用程式控管型警示。

![Microsoft 365 合規性中心的應用程式控管警示摘要頁面](..\media\manage-app-protection-governance\mapg-cc-alerts.png)

每個列出的警示都有下列資訊：

- **警示名稱**：異常行為的類型。
- **應用程式名稱**：產生警示的應用程式。
- **嚴重性**：應用程式控管針對它所建立警示所指派的嚴重性，或產生警示的應用程式原則嚴重性。
- **來源**：警示的來源，可能來自原則 (使用者建立的原則)、偵測 (內建偵測原則) 或 MCAS。
- **狀態**：[新] 表示尚未指派狀態的警示。 狀態指派後，狀態為 [進行中] 表示正在調查，或 [已解決] 表示已透過自動或手動修復而解決的警示。
- **建立日期**：由應用程式控管偵測或透過應用程式原則產生警示的日期。 所有顯示的日期都是 Microsoft 365 合規性中心的當地時區。
- **上次活動**：上次警示狀態變更的日期。 所有顯示的日期都是 Microsoft 365 合規性中心的當地時區。

警示清單預設會以 [建立日期] 排序。 若要根據另一個屬性排序清單，請選取屬性名稱。

您也可以將目前的警示清單匯出為逗號分隔值 (CSV) 檔案。 例如，您可以在 Microsoft Excel 中開啟 CVS 檔案，然後根據 [嚴重性]，然後是 [建立日期] 排序警示清單。

## <a name="next-step"></a>下一個步驟

[補救應用程式威脅。](app-governance-detect-remediate-detect-threats.md)
