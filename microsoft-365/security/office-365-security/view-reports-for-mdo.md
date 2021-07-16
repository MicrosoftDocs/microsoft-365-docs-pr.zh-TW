---
title: 檢視適用於 Office 365 的 Microsoft Defender 報告
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 系統管理員可以瞭解如何針對 Microsoft 365 Defender 入口網站中提供的 Office 365 報告尋找和使用 Defender。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e8bb03202139137adf55c4c10230b1c4e99253ba
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454718"
---
# <a name="view-defender-for-office-365-reports-in-the-microsoft-365-defender-portal"></a>在 Microsoft 365 Defender 入口網站中查看 Office 365 報表的 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

適用于 Office 365 組織的 Microsoft Defender (例如，Microsoft 365 E5 訂閱或 microsoft defender for Office 365 plan 1 或 microsoft defender for Office 365 plan 2 附加元件) 包含各種安全性相關的報表。 如果您有 [必要的許可權](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)，您可以在 Microsoft 365 Defender 入口網站中透過 **報告** \> **&** 共同作業 \> **電子郵件 &** 共同作業報告來查看這些報告。 若要直接移至 [ **電子郵件 &** 共同作業報告] 頁面上，開啟 <https://security.microsoft.com/emailandcollabreport> 。

![Microsoft 365 Defender 入口網站中的電子郵件 & 共同作業報告] 頁面](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> 不需要 Office 365 Defender 的電子郵件安全性報告會在[Microsoft 365 Defender 入口網站中的「查看電子郵件安全性報告](view-email-security-reports.md)」中說明加以說明。
>
> 與郵件流程相關的報告現在位於 Exchange 系統管理中心 (EAC) 。 如需這些報告的詳細資訊，請參閱[新 Exchange 系統管理中心的郵件流程報告](/exchange/monitoring/mail-flow-reports/mail-flow-reports)。

## <a name="safe-attachments-file-types-report"></a>保管庫附件檔案類型報告

> [!NOTE]
> **保管庫附件檔案類型報告** 會最終消失。 「 [威脅防護狀態」報告](#threat-protection-status-report)中提供相同的資訊。

## <a name="safe-attachments-message-disposition-report"></a>保管庫附件郵件處理報告

> [!NOTE]
> **保管庫附件郵件處理報告** 會最後消失。 「 [威脅防護狀態」報告](#threat-protection-status-report)中提供相同的資訊。

## <a name="mail-latency-report"></a>郵件延遲報告

**郵件延遲報告** 會向您顯示組織內的郵件傳遞和引爆延遲的匯總視圖。 服務中的郵件傳遞時間受到多種因素的影響，而且絕對傳遞時間（秒）通常不是成功或問題的明確指示。 在一天內的傳遞時間可能會被視為另一天的平均傳遞時間，或反過來。 這會嘗試根據對其他郵件的觀察傳遞時間的統計資料來傳遞郵件。

不包括用戶端和網路延遲。

若要查看報告，請開啟 [Microsoft 365 Defender 入口網站](https://security.microsoft.com)，然後移至 [**報告** \> **電子郵件 &** 共同作業 \> **電子郵件 &** 共同作業報告]。 在 [ **電子郵件 &** 共同作業報告] 頁面上，尋找 [ **郵件延遲報告** ]，然後按一下 [ **查看詳細資料**]。 若要直接前往報表，請開啟 <https://security.microsoft.com/mailLatencyReport> 。

![「電子郵件 & 協同報告」頁面上的郵件延遲報告構件](../../media/mail-latency-report-widget.png)

在 [ **郵件延遲報告** ] 頁面上，[ **郵件延遲報告** ] 頁面上提供下列索引標籤：

- 第 **50 個百分點**：這是郵件傳遞時間的中間部分。 您可以將此值視為平均傳遞時間。 預設會選取此索引標籤。
- **90%**：這表示郵件傳遞的高延遲。 只有10% 的郵件花費的時間超過此值才能傳遞。
- **99th 百分點**：這表示郵件傳遞的最高延遲。

不論選取的索引標籤為何，圖表都會顯示組織成下列類別的郵件：

- **郵件傳遞延遲**
- **Detonations**

當您將游標移到圖表中的某個類別時，您可以查看每個類別中的延遲明細。

![第50百分位數郵件延遲報告的視圖](../../media/mail-latency-report-50th-percentile-view.png)

如果您按一下 [ **篩選**]，您可以透過下列值來篩選圖表和詳細資料表格：

- **日期 (UTC)**： **開始日期** 和 **結束日期**
- **郵件視圖**：下列其中一個值：
  - **所有郵件**
  - **包含附件或 URLs 的郵件**
  - **引爆郵件**

當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。

在圖表下方的 [詳細資料] 表格中，可使用下列資訊：

- **日期 (UTC)**
- **百分位數**： **50**、 **90** 或 **99**
- **訊息計數**
- **整體延遲**

## <a name="threat-protection-status-report"></a>威脅防護狀態報告

「**威脅防護狀態** 報告」是單一的視圖，可透過 [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) 和 Microsoft Defender for Office 365，彙集惡意內容和惡意電子郵件的相關資訊。 如需詳細資訊，請參閱 [威脅防護狀態報表](view-email-security-reports.md#threat-protection-status-report)。

## <a name="url-threat-protection-report"></a>URL 威脅防護報告

**url 威脅防護報告** 可提供偵測到之威脅的摘要和趨勢視圖，以及在 URL 按一下上做為 [保管庫連結](safe-links.md)的一部分所採取的動作。 在套用保管庫連結原則的使用者上，按一下 [不 **追蹤使用者點擊**] 選項時，此報告不會有按一下資料。

若要查看報告，請開啟 [Microsoft 365 Defender 入口網站](https://security.microsoft.com)，然後移至 [**報告** \> **電子郵件 &** 共同作業 \> **電子郵件 &** 共同作業報告]。 在 [ **電子郵件 &** 共同作業報告] 頁面上，找到 [ **URL 保護] 頁面** ，然後按一下 [ **查看詳細資料**]。 若要直接前往報表，請開啟 <https://security.microsoft.com/reports/URLProtectionActionReport> 。

![電子郵件 & 協同報告] 頁面上的 URL 保護報告構件](../../media/url-protection-report-widget.png)

下列各節將說明 [ **URL 威脅防護** 報告] 頁面上可用的視圖。

> [!NOTE]
> 這是一項 *保護趨勢報告*，表示資料代表較大資料集的趨勢。 因此，在這種情況下，圖表中的資料並不是即時的，但是 [詳細資料] 表格中的資料是，因此您可能會看到兩者之間的差異稍有不同。 圖表每四小時重新整理一次，並包含過去90天的資料。

### <a name="view-data-by-url-click-protection-action"></a>依 URL 查看資料按一下 [保護動作]

![Url 威脅防護報告中的 URL 按一下保護動作視圖](../../media/url-threat-protection-report-url-click-protection-action-view.png)

**依 URL 的查看資料按一下 [保護動作**] 視圖，會顯示組織中使用者的 URL 按一下數目，以及按一下的結果。

- **允許**：允許使用者流覽至 URL。
- 已 **封鎖**：已封鎖使用者流覽至 URL。
- **封鎖並按一下透過**：使用者已選擇繼續導覽 URL。
- 在 **掃描期間按一下流覽**：使用者已在掃描完成之前按一下連結。

按一下表示使用者已透過封鎖頁面按一下至惡意網站 (系統管理員可以停用保管庫連結原則) 中的按一下。

如果您按一下 [ **篩選**]，您可以在出現的浮出控制項中選取下列一或多個值，以修改報告和詳細資料表格：

- **日期 (UTC)**： **開始日期** 和 **結束日期**
- **偵測**：
  - **允許**
  - **封鎖**
  - **封鎖並按一下**
  - **在掃描期間按一下**
- **網域**：報告結果中列出的 URL 網域。
- **收件者**

當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。

圖表下方的 [詳細資料] 表格提供下列最近7天內所有按一下動作的近乎即時視圖：

- **按一下 [時間]**
- **使用者**
- **URL**
- **Action**
- **應用程式**

### <a name="view-data-by-url-click-by-application"></a>依 URL 查看資料依應用程式按一下

![URL 威脅防護報告中的 [依應用程式視圖按一下 URL]](../../media/url-threat-protection-report-url-click-by-application-view.png)

**依 URL 的 View data 依序按一下 [應用程式** 視圖]，會顯示支援保管庫連結的應用程式的 URL 按一下數目：

- **電子郵件用戶端**
- **PowerPoint**
- **Word**
- **Excel**
- **OneNote**
- **Visio**
- **Teams**
- **別人**

如果您按一下 [ **篩選**]，您可以在出現的浮出控制項中選取下列一或多個值，以修改報告和詳細資料表格：

- **日期 (UTC)**： **開始日期** 和 **結束日期**
- **偵測**：圖表中可用的應用程式。
- **網域**：報告結果中列出的 URL 網域。
- **收件者**

當您完成設定篩選 **時，請按一下 [** 套用]、[ **取消**] 或 [ **清除篩選**]。

圖表下方的 [詳細資料] 表格提供下列最近7天內所有按一下動作的近乎即時視圖：

- **按一下 [時間]**
- **使用者**
- **URL**
- **Action**
- **應用程式**

## <a name="additional-reports-to-view"></a>要查看的其他報告

除了本文所述的報告之外，還有其他幾個報告可供使用，如下表所述：

<br>

****

|報告|主題|
|---|---|
|**Explorer** (microsoft defender for Office 365 plan 2) 或 **即時** 偵測 (Microsoft defender for Office 365 Plan 1) |[威脅總管 (及即時偵測)](threat-explorer.md)|
|不需要 Office 365 Defender 的電子郵件安全性報告|[在 Microsoft 365 Defender 入口網站中查看電子郵件安全性報告](view-email-security-reports.md)|
|Exchange 系統管理中心的郵件流程報告 (EAC) |[新 Exchange 系統管理中心的郵件流程報告](/exchange/monitoring/mail-flow-reports/mail-flow-reports)|
|

PowerShell 報告 Cmdlet：

<br>

****

|報告|主題|
|---|---|
|排名最前面的寄件者及收件者|[Get-MailTrafficTopReport](/powershell/module/exchange/get-mailtraffictopreport) <p> [Get-MailTrafficSummaryReport](/powershell/module/exchange/get-mailtrafficsummaryreport)|
|主要惡意程式碼|[Get-MailTrafficSummaryReport](/powershell/module/exchange/get-mailtrafficsummaryreport)|
|郵件流量|[MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport) <p> [MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport)|
|安全連結|[SafeLinksAggregateReport](/powershell/module/exchange/get-safelinksaggregatereport) <p> [SafeLinksDetailReport](/powershell/module/exchange/get-safelinksdetailreport)|
|遭破壞的使用者|[CompromisedUserAggregateReport](/powershell/module/exchange/get-compromiseduseraggregatereport) <p> [CompromisedUserDetailReport](/powershell/module/exchange/get-compromiseduserdetailreport)|
|郵件流程狀態|[MailflowStatusReport](/powershell/module/exchange/get-mailflowstatusreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a>流覽 Office 365 報表的 Defender 時，需要哪些許可權？

為了查看和使用本文所述的報表，您必須是 Microsoft 365 Defender 入口網站中下列其中一個角色群組的成員：

- **組織管理**
- **安全性系統管理員**
- **安全性讀取者**
- **全域讀取者**

如需詳細資訊，請參閱 [Microsoft 365 Defender 入口網站中的權限](permissions-microsoft-365-security-center.md)。

**附注**：將使用者新增至 Microsoft 365 系統管理中心中對應的 Azure Active Directory 角色，可為使用者提供 Microsoft 365 Defender 入口網站中的必要許可權 _，以及_ Microsoft 365 中其他功能的許可權。 如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。

## <a name="what-if-the-reports-arent-showing-data"></a>如果報告未顯示資料，該怎麼辦？

如果您未在 Office 365 報告中看到您的 Defender 資料，請仔細檢查您的原則設定是否正確。 您的組織必須已定義[保管庫連結原則](set-up-safe-links-policies.md)及[保管庫附件原則](set-up-safe-attachments-policies.md)，才能使用 Defender，Office 365 保護功能即就地。 另請參閱 [反垃圾郵件和反惡意程式碼保護](anti-spam-and-anti-malware-protection.md)。

## <a name="related-topics"></a>相關主題

[Microsoft 365 Defender 入口網站中的智慧報告和洞察力](reports-and-insights-in-security-and-compliance.md)

[角色許可權 (Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
