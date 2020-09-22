---
title: 查看高級威脅防護的報告
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
description: 在安全性與合規性中心尋找及使用 Office 365 的「高級威脅防護」報告 &amp; 。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 90da02c8aa3d50f62bdf4be8c466962da828b23d
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196582"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a>檢視 Office 365 進階威脅防護的報告

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Office 365 Advanced 威脅防護 (ATP) 組織 (例如，Microsoft 365 E5 訂閱或 ATP Plan 1 或 ATP Plan 2 附加元件) 包含各種與安全性相關的報表。 如果您有 [必要的許可權](#what-permissions-are-needed-to-view-the-atp-reports)，您可以移至 [ **報表**] \> **儀表板**，在安全性 & 規範中心中查看這些報告。 若要直接移至 [報告] 儀表板，請開啟] <https://protection.office.com/insightdashboard> 。

![安全性 & 規範中心內的報告儀表板](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="advanced-threat-protection-file-types-report"></a>進階威脅防護檔案類型報告

「 **高級威脅防護檔案類型報告** 」報告會顯示由 [ATP 安全附件](atp-safe-attachments.md)偵測為惡意的檔案類型。

 報表的匯總視圖允許90天的篩選，而詳細資料檢視只允許10天的篩選。

若要查看報告，請開啟 [安全性 & 合規性中心](https://protection.office.com)，移至 [ **報告**] \> **儀表板** ，然後選取 [ **Office ATP 檔案類型**]。 若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=ATPFileReport> 。

![報表儀表板中的 Office ATP 檔案類型構件](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> 您也可以在「 [高級威脅防護郵件](#advanced-threat-protection-message-disposition-report)處理」報告中使用此報告中的資訊。

### <a name="report-view-for-the-advanced-threat-protection-file-types-report"></a>高級威脅防護檔案類型報告的報表檢視

可供使用的視圖如下：

- **資料查看依據：** 檔案：此圖表包含下列資訊：

  - **惡意 Excel 附件**
  - **惡意的 Flash 附件**
  - **惡意的 PDF 附件**
  - **惡意 PowerPoint 附件**
  - **惡意 URLs**
  - **惡意的 Word 附件**
  - **惡意可執行附件**
  - **別人**

  當您將滑鼠停留在特定日期 (資料點) 時，您可以看到 [ATP 安全附件](atp-safe-attachments.md) 和 [EOP 中的反惡意程式碼保護](anti-malware-protection.md)所偵測到的惡意檔案類型細目。

  ![ATP 檔案類型報告中的檔查看](../../media/atp-file-types-report-file-view.png)

  如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：

  - **開始日期** 和 **結束日期**
  - 圖表中顯示的相同檔案類型值。

- **資料查看方式：訊息**：此圖表包含下列資訊：

  - **封鎖存取**
  - **取代郵件**
  - **監控的郵件**
  - 以**動態電子郵件傳遞取代**：如需詳細資訊，請參閱[使用 ATP 安全附件動態傳遞和預覽](dynamic-delivery-and-previewing.md)。

  ![ATP 檔案類型報告中的郵件視圖](../../media/atp-file-types-report-message-view.png)

  如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：

  - **開始日期** 和 **結束日期**
  - 圖表中可用的相同郵件處置值，以及已傳遞的其他 **郵件** 值。

### <a name="details-table-view-for-the-advanced-threat-protection-file-types-report"></a>高級威脅防護檔案類型報告的詳細資料表格視圖

如果您按一下 [ **查看詳細資料] 表格**，此報告可提供最近10天內所有按一下動作的近乎即時視圖。 顯示的資訊取決於您所看到的圖表：

- **資料查看依據：** 檔案：

  - **Date**
  - **收件者位址**
  - **寄件者位址**
  - **郵件識別碼**：郵件頭的 **Message-ID** 標頭欄位中可用，且應該是唯一的。 範例值 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (記下角括弧) 。
  - **File**

  如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：

  - **開始日期** 和 **結束日期**
  - 圖表中顯示的相同檔案類型值。

- **資料查看依據：訊息**：

  - **Date**
  - **收件者位址**
  - **寄件者位址**
  - **郵件識別碼**
  - **File**
  - **Subject**

  如果您按一下 [ **篩選**]，您可以使用下列篩選器修改結果：

  - **開始日期** 和 **結束日期**
  - 圖表中可用的相同郵件處置值，以及已傳遞的其他 **郵件** 值。

若要回到 [報表] 視圖，請按一下 [ **view report**]。

## <a name="advanced-threat-protection-message-disposition-report"></a>進階威脅防護郵件處置報告

**ATP 郵件**處理報告會顯示偵測到有惡意內容的電子郵件所採取的動作。

若要查看報告，請開啟 [安全性 & 規範中心](https://protection.office.com)，移至 [ **報告**] \> **儀表板** ，然後選取 [ **Office ATP 郵件**處理]。 若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=ATPMessageReport> 。

![報表儀表板中的 Office 365 ATP 郵件處置小工具](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> 您也可以在「 [高級威脅防護檔案類型」報告](#advanced-threat-protection-file-types-report)中使用此報告中的資訊。

### <a name="report-view-for-the-advanced-threat-protection-message-disposition-report"></a>高級威脅防護郵件處理報告的報表檢視

可供使用的視圖如下：

- **資料查看方式：訊息**：此圖表包含下列資訊：

  - **封鎖存取**
  - **取代郵件**
  - **監控的郵件**
  - 以**動態電子郵件傳遞取代**：如需詳細資訊，請參閱[使用 ATP 安全附件動態傳遞和預覽](dynamic-delivery-and-previewing.md)。

  ![ATP 檔案類型報告中的郵件視圖](../../media/atp-file-types-report-message-view.png)

  如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：

  - **開始日期** 和 **結束日期**
  - 圖表中可用的相同郵件處置值，以及已傳遞的其他 **郵件** 值。

- **資料查看依據：** 檔案：此圖表包含下列資訊：

  - **惡意 Excel 附件**
  - **惡意的 Flash 附件**
  - **惡意的 PDF 附件**
  - **惡意 PowerPoint 附件**
  - **惡意 URLs**
  - **惡意的 Word 附件**
  - **惡意可執行附件**
  - **別人**

  當您將滑鼠停留在特定日期 (資料點) 時，您可以看到 [ATP 安全附件](atp-safe-attachments.md) 和 [EOP 中的反惡意程式碼保護](anti-malware-protection.md)所偵測到的惡意檔案類型細目。

  ![ATP 檔案類型報告中的檔查看](../../media/atp-file-types-report-file-view.png)

  如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：

  - **開始日期** 和 **結束日期**
  - 圖表中顯示的相同檔案類型值。

### <a name="details-table-view-for-the-advanced-threat-protection-message-disposition-report"></a>高級威脅防護郵件處理報告的詳細資料表格視圖

如果您按一下 [ **查看詳細資料] 表格**，此報告可提供最近10天內所有按一下動作的近乎即時視圖。 顯示的資訊取決於您所看到的圖表：

- **資料查看依據：訊息**：

  - **Date**
  - **收件者位址**
  - **寄件者位址**
  - **郵件識別碼**
  - **File**
  - **Subject**

  如果您按一下 [ **篩選**]，您可以使用下列篩選器修改結果：

  - **開始日期** 和 **結束日期**
  - 圖表中可用的相同郵件處置值，以及已傳遞的其他 **郵件** 值。

- **資料查看依據：** 檔案：

  - **Date**
  - **收件者位址**
  - **寄件者位址**
  - **郵件識別碼**
  - **File**

  如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：

  - **開始日期** 和 **結束日期**
  - 圖表中顯示的相同檔案類型值。

若要回到 [報表] 視圖，請按一下 [ **view report**]。

## <a name="threat-protection-status-report"></a>威脅防護狀態報告

「 **威脅防護狀態** 報告」是單一的視圖，可彙集 [Exchange ONLINE protection](exchange-online-protection-overview.md) (EOP) 和 Office 365 ATP 所偵測到和封鎖的惡意內容和惡意電子郵件資訊。 如需詳細資訊，請參閱 [威脅防護狀態報表](view-email-security-reports.md#threat-protection-status-report)。

## <a name="url-threat-protection-report"></a>URL 威脅防護報告

**Url 威脅防護報告**可提供偵測威脅的摘要和趨勢視圖，以及在 URL 按一下上進行的動作，做為[ATP 安全連結](atp-safe-links.md)的一部分。 若已套用安全連結原則的使用者沒有選取 [不 **追蹤使用者點擊** ] 選項，則此報告將不會有按一下其資料的使用者。

若要查看報告，請開啟 [安全性 & 合規性中心](https://protection.office.com)，移至 [ **報告**] \> **儀表板** ，然後選取 [ **URL 保護報告**]。 若要直接前往報表，請開啟 <https://protection.office.com/reportv2?id=URLProtectionActionReport> 。

![報表儀表板中的 URL 保護報告構件](../../media/url-protection-report-widget.png)

> [!NOTE]
> 這是一項 *保護趨勢報告*，表示資料代表較大資料集的趨勢。 因此，在這種情況下，不會即時提供匯總視圖中的資料，但 [詳細資料] 表格視圖中的資料則是如此，您可能會看到這兩種視圖之間稍有差異。

### <a name="report-view-for-the-url-threat-protection-report"></a>URL 威脅防護報告的報表檢視

**URL 威脅防護**報告有兩個匯總的視圖，每四個小時都會重新整理一次，以顯示過去90天的資料：

- **URL 按一下保護動作**：顯示組織中的使用者按下 URL 按一下數目及按一下的結果：

  - **封鎖** (禁止使用者流覽至 URL) 
  - **封鎖並按一下**
  - **在掃描期間按一下**

  按一下表示使用者已透過封鎖頁面按一下至惡意網站 (系統管理員可以停用 [安全連結) 原則] 中的 click。

  如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：

  - **開始日期** 和 **結束日期**
  - 可使用的 [保護動作]，加上 **允許 (使用者** 流覽至 URL) 的值。

  ![Url 威脅防護報告中的 URL 按一下保護動作視圖](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- **依應用程式按一下 url**：會顯示支援 OFFICE 365 ATP 安全連結之應用程式的 url 按一下數目。

  - **電子郵件用戶端**
  - **PowerPoint**
  - **Word**
  - **Excel**
  - **OneNote**
  - **Visio**
  - **Teams**
  - **其他**

  如果您按一下 [ **篩選**]，您可以使用下列篩選器修改報告：

  - **開始日期** 和 **結束日期**
  - 可用的應用程式。

### <a name="details-table-view-for-the-url-threat-protection-report"></a>URL 威脅防護報告的詳細資料表格視圖

如果您按一下 [ **查看詳細資料] 表格**，則報告會提供最近7天內組織內所有按一下動作的近乎即時視圖，其詳細資料如下：

- **按一下 [時間]**
- **使用者**
- **URL**
- **Action**
- **App**

如果您按一下 [詳細資料] 表格視圖中的 [**篩選器**]，可以篩選與報表檢視中相同的準則，**以及以逗號分隔的****網域**或收件者。

若要回到 [報表] 視圖，請按一下 [ **view report**]。

## <a name="additional-reports-to-view"></a>要查看的其他報告

除了本主題所述的 ATP 報告之外，還有其他幾個報告可供使用，如下表所述：

****

|報告|主題|
|---|---|
|**Explorer** (atp 方案 2) 或 **即時** 偵測 (ATP plan 1) |[威脅總管 (及即時偵測)](threat-explorer.md)|
|**電子郵件安全性報告**，例如主要寄件者和收件者報告、冒名郵件報告和垃圾郵件偵測報告。|[檢視安全性與合規性中心內的電子郵件安全性報告](view-email-security-reports.md)|
|**郵件流程報告**，例如轉寄報告、郵件流程狀態報表，以及主要寄件者和收件者報告。|[在安全性 & 規範中心內，查看郵件流程報告](view-mail-flow-reports.md)|
|**ATP 安全連結的 URL 追蹤** (只 PowerShell) 。 此 Cmdlet 的輸出會顯示在過去7天內 ATP 安全連結動作的結果。|[Get-UrlTrace](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|**EOP 和 ATP (的郵件流量結果** 只 PowerShell) 。 此 Cmdlet 的輸出包含網域、日期、事件種類、方向、動作和郵件數目的相關資訊。|[MailTrafficATPReport](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|**EOP 和 ATP 偵測的郵件詳細資料包告** (僅 PowerShell) 。 此 Cmdlet 的輸出包含有關電子郵件或檔案中惡意檔案或 URLs、網路釣魚企圖、模仿及其他潛在威脅的詳細資料。|[MailDetailATPReport](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a>查看 ATP 報表所需的許可權為何？

若要查看和使用本主題中所述的報表， **您必須為安全性與 &amp; 合規性中心和 Exchange 系統管理中心指派適當的角色**。

- 針對安全性 & 合規性中心，您必須已指派下列角色之一：

  - 組織管理
  - 安全性系統管理員 (這可以在 Azure Active Directory 系統管理中心指派 ([https://aad.portal.azure.com](https://aad.portal.azure.com)))
  - 安全性操作員 (可以在 Azure Active Directory 系統管理中心中指派 ([https://aad.portal.azure.com](https://aad.portal.azure.com)) # A3
  - 安全性讀取者

- 針對 Exchange Online，您必須在 Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) 或 PowerShell Cmdlet (請參閱 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)) 受指派下列其中一個角色：

  - 組織管理
  - 僅檢視組織管理
  - 僅檢視收件者角色
  - 合規性管理

若要深入了解，請參閱下列資源：

- [安全性與合規性中心的權限](permissions-in-the-security-and-compliance-center.md)

- [Exchange Online 中的功能權限](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a>如果報告未顯示資料，該怎麼辦？

如果您未看到 ATP 報告中的資料，請仔細檢查您的原則設定是否正確。 您的組織必須已定義 [Atp 安全連結原則](set-up-atp-safe-links-policies.md) 和 [atp 安全附件原則](set-up-atp-safe-attachments-policies.md) ，才能進行 atp 保護。 另請參閱 [Office 365 中的反垃圾郵件和反惡意程式碼保護](anti-spam-and-anti-malware-protection.md)。

## <a name="related-topics"></a>相關主題

[安全性與合規性中心內的智慧型報表和深入解析](reports-and-insights-in-security-and-compliance.md)
  
[ (Azure Active Directory 的角色許可權](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
