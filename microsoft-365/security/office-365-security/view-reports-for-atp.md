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
ms.openlocfilehash: af5844cf05d14e34059a26291d2034187439ec56
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208486"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a>檢視 Office 365 進階威脅防護的報告

如果您的組織有[Office 365 高級威脅防護](office-365-atp.md)（ATP），而且您有[必要的許可權](#what-permissions-are-needed-to-view-the-atp-reports)，您可以在安全性與 &amp; 合規性中心使用數個 ATP 報告。 （移至**報表** \>**儀表板**。）

![安全性與 &amp; 合規性中心儀表板可協助您查看高級威脅防護的運作情形](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

ATP 報告包含下列專案：

- [威脅防護狀態報告](#threat-protection-status-report)
- [ATP 檔案類型報告](#atp-file-types-report)
- [ATP 郵件處置報告](#atp-message-disposition-report)
- [即時偵測或 Explorer](threat-explorer.md) （取決於您是否有 OFFICE 365 ATP 方案1或2）
- ...[等等](#additional-reports-to-view)。

請閱讀本文，以取得 ATP 報表及其用法的概覽。

## <a name="threat-protection-status-report"></a>威脅防護狀態報告

「**威脅防護狀態**報告」是單一的視圖，可彙集[Exchange Online Protection](exchange-online-protection-overview.md) （EOP）和[Office 365 ATP](office-365-atp.md)所偵測到和封鎖的惡意內容和惡意電子郵件資訊。 此報告可用於查看一段時間內的偵測（最多90天），並可讓安全性管理員識別趨勢或判斷是否需要調整原則。

該報告提供包含惡意內容的獨特電子郵件的匯總計數，例如檔案或網站位址（URLs），該惡意內容已封鎖反惡意程式碼引擎、[零小時的自動清除（ZAP）](zero-hour-auto-purge.md)和 atp 功能（如[atp 安全連結](atp-safe-links.md)、 [atp 安全附件](atp-safe-attachments.md)及[atp 反網路釣魚](set-up-anti-phishing-policies.md)）。

資訊的篩選和細分可讓您在此報告中進一步細化資訊的類別。 具體而言，**電子郵件** \> **網路釣魚**和**電子郵件** \> **惡意程式碼視圖**中也會包含「細分者」功能表。 它會將資料分解成：

|||
|---|---|
|依偵測類型|哪些原則會協助捕捉這些威脅？|
|依偵測技術|哪些基本的 Microsoft 技術會陷入威脅？|
|依傳遞狀態|電子郵件被偵測為威脅時會發生什麼事？|
|

> [!TIP]
> 電子郵件 > 網路釣魚 |惡意程式碼視圖對顯示的偵測技術有細微的損害，其類別如*ATP 產生的檔案信譽*、檔案*引爆*、 *URL 引爆*、*反欺騙性： DMARC 失敗*，例如，明確確切指出您的組織攔截威脅的確切功能 led。

![[威脅防護狀態報表] 下拉式清單顯示「中斷者」。](../../media/tp-threatProtectStatRpt-BreakDownBy.png)

這些視圖可讓您透過按鈕按一下（在**電子郵件** \> **網路釣魚**程式、**電子郵件** \> **惡意**代碼和**內容** \> **惡意**代碼視圖）來匯出選項。 匯出至電腦的匯總資料可以在 Excel 中開啟。

![此圖形顯示匯出為惡意程式碼視圖功能表中的選項、建立排程和要求報告之間的選項。](../../media/tp-threatProtectStatRpt-BreakDownByExport.png)

**附注**：**網路釣魚**和**惡意**代碼可以匯出的專案數上限，都是在10000。 如果您匯出的是視圖，則只會匯出最近的10000專案。

「一覽」和「電子郵件」視圖會在處理時間內（而不是24小時）顯示資訊（要求重新）。 增加的速度是清晰的信號）！

> [!NOTE]
> 「威脅防護狀態」報告適用于具有[Office 365 ATP](office-365-atp.md)或[Exchange Online Protection](exchange-online-protection-overview.md)（EOP）的客戶;不過，針對 ATP 客戶顯示在威脅防護狀態報表中的資訊，其可能會包含與客戶可能看到的 EOP 不同的資料。 例如，ATP 客戶的「威脅防護狀態報表」會包含[SharePoint 線上、OneDrive 或 Microsoft 小組中偵測到之惡意](atp-for-spo-odb-and-teams.md)檔案的相關資訊。 這類資訊專用於 ATP，所以具有 EOP 但不是 ATP 的客戶將無法在威脅防護狀態報表中看到這些詳細資料。

若要查看「威脅防護狀態」報告，請在[安全性與 &amp; 合規性中心](https://protection.office.com)，移至 [**報告**] \> **儀表板** \> **威脅防護狀態**。

![ATP 威脅防護狀態報表](../../media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)

若要取得一天的詳細狀態，請將游標懸停在圖形上方。

![一天的 ATP 威脅防護狀態資料](../../media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)

「威脅防護狀態」報告預設會顯示過去7天的資料。 不過，您可以選擇 [**篩選**] 並變更日期範圍，以查看最多90天的資料。 （如果您是使用試用訂閱，則可能會限制為30天的資料。）

![ATP 威脅防護狀態篩選](../../media/4f703369-642b-402b-9758-b9c828283410.png)

您也可以使用 [ **View data by** ] 功能表來變更報表中所顯示的資訊。

![查看 ATP 威脅防護狀態報表的選項](../../media/4959bf8c-d192-4542-b00b-184e101e7513.png)

## <a name="url-protection-status-report"></a>URL 保護狀態報表

這份報告是以每次按一下來收集的資料，以及偵測到的威脅（而大多數其他電子郵件威脅相關的報告為每一封郵件資料）。 此報告的設計目的是顯示來自電子郵件和檔中每次按一下的超連結的威脅。 有兩種觀點：

|||
|---|---|
|URL 按一下保護動作|查看封鎖的 URLs 數目、封鎖但以使用者的按一下權覆寫，使用者會以點擊和允許的方式覆寫。|
|依應用程式按一下 URL|請參閱已按一下 URL 的應用程式。|
|

在 [詳細資料] 表格中，您將可以看到有關按一下時間和使用者資訊的詳細資訊。 最後，請記住 URL 保護狀態報表顯示來自 ATP 安全連結功能的保護，所以只有已啟用 ATP 安全連結的客戶才能看到此報告上會反映的資料。

> [!NOTE]
> 這是一項*保護趨勢報告*，表示資料代表較大資料集的趨勢。 因此，在這種情況下，不會即時提供匯總視圖中的資料，但 [詳細資料] 表格視圖中的資料則是如此，您可能會看到這兩種視圖之間稍有差異。

## <a name="atp-file-types-report"></a>ATP 檔案類型報告

**Atp 檔案類型**報告會顯示由[ATP 安全附件](atp-safe-attachments.md)偵測為惡意的檔案類型。

若要查看此報告，請在[安全性與 &amp; 合規性中心](https://protection.office.com)，移至 [**報告**] \> **儀表板** \> **ATP 檔案類型**。

![ATP 檔案類型報告](../../media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
當您將游標移到某一天時，您可以看到[ATP 安全附件](atp-safe-attachments.md)和[反垃圾郵件 &amp; 反惡意程式碼保護](anti-spam-and-anti-malware-protection.md)偵測到的惡意檔案類型細目。
  
![ATP 檔案類型一天的報告資料](../../media/10d18428-699a-41d2-a73e-be3a8214ada1.png)

## <a name="atp-message-disposition-report"></a>ATP 郵件處置報告

**ATP 郵件**處理報告會顯示偵測到有惡意內容的電子郵件所採取的動作。

若要查看此報告，請在[安全性與 &amp; 合規性中心](https://protection.office.com)，移至 [**報告**] \> **儀表板** \> **ATP 郵件部署**。

![ATP 郵件處置報告](../../media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)

當您將游標移到圖表中的某個列上方時，您就會看到針對該天所偵測到的電子郵件所採取的動作。

![一天的 ATP 郵件處置報告資料](../../media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)

## <a name="additional-reports-to-view"></a>要查看的其他報告

除了本文所述的 ATP 報告之外，還有其他幾個報告可供使用，如下表所述：

|||
|---|---|
|**報告**|**詳細資料**|
|**瀏覽器**或**即時**偵測：（Office 365 ATP Plan 2 客戶具有 Explorer;Office 365 ATP Plan 1 客戶具備即時偵測。|[威脅總管 (及即時偵測)](threat-explorer.md)|
|**電子郵件安全性報告**，例如主要寄件者和收件者報告、冒名郵件報告和垃圾郵件偵測報告。|[檢視安全性與合規性中心內的電子郵件安全性報告](view-email-security-reports.md)|
|**ATP 安全連結 URL 追蹤**：（這是您使用 PowerShell 所產生的報表）。此報告顯示在過去七（7）天內 ATP 安全連結動作的結果。|[Get-UrlTrace Cmdlet 參考](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-urltrace)|
|**EOP 和 ATP 結果**：（這是您使用 PowerShell 所產生的自訂報告）。 此報告包含資訊，例如網域、日期、事件種類、方向、動作和郵件數目。|[MailTrafficATPReport Cmdlet 參考](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport)|
|**EOP 和 ATP**偵測：（這是您使用 PowerShell 所產生的自訂報告）。 此報告包含有關電子郵件或檔案中惡意檔案或 URLs、網路釣魚企圖、模仿及其他潛在威脅的詳細資料。|[MailDetailATPReport Cmdlet 參考](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a>查看 ATP 報表所需的許可權為何？

為了查看和使用本文所述的報告，**您必須為安全性與 &amp; 合規性中心和 Exchange 系統管理中心指派適當的角色**。

- 針對「安全性與合規性中心」，您必須受指派下列其中一個角色：

  - 組織管理
  - 安全性系統管理員 (這可以在 Azure Active Directory 系統管理中心指派 ([https://aad.portal.azure.com](https://aad.portal.azure.com)))
  - 安全操作員（可以在 Azure Active Directory 系統管理中心內 [https://aad.portal.azure.com](https://aad.portal.azure.com) 指派）
  - 安全性讀取者

- 針對 Exchange Online，您必須在 Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) 或 PowerShell Cmdlet (請參閱 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)) 受指派下列其中一個角色：

  - 組織管理
  - 僅檢視組織管理
  - 僅檢視收件者角色
  - 合規性管理

若要深入了解，請參閱下列資源：

- [安全性與 &amp; 合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)

- [Exchange Online 中的功能權限](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a>如果報告未顯示資料，該怎麼辦？

如果您未看到 ATP 報告中的資料，請仔細檢查您的原則設定是否正確。 您的組織必須已定義[Atp 安全連結原則](set-up-atp-safe-links-policies.md)和[atp 安全附件原則](set-up-atp-safe-attachments-policies.md)，才能進行 atp 保護。 另請參閱[Office 365 中的反垃圾郵件和反惡意程式碼保護](anti-spam-and-anti-malware-protection.md)。

## <a name="related-topics"></a>相關主題

[安全性與 &amp; 合規性中心內的報告與深入瞭解](reports-and-insights-in-security-and-compliance.md)
  
[在安全性與 &amp; 合規性中心建立報表的排程](create-a-schedule-for-a-report.md)

[在安全性與 &amp; 合規性中心內設定及下載自訂報告](set-up-and-download-a-custom-report.md)

[角色許可權（Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
