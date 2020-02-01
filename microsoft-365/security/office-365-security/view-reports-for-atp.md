---
title: 檢視報表的 Office 365 進階威脅防護，惡意程式碼報告，釣魚程式報告、 遭入侵的帳戶、 URL 保護狀態、 威脅報告、 報告威脅
f1.keywords:
- CSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/10/2020
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
description: 尋找並使用 Office 365 進階威脅防護中的安全性報告&amp;合規性中心。
ms.openlocfilehash: a1db932dda8b49d2d17805e605e11bc654c0e318
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598070"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a>檢視 Office 365 進階威脅防護的報告

如果您的組織有[Office 365 進階威脅防護](office-365-atp.md)(ATP)，而且您具有[必要權限](#what-permissions-are-needed-to-view-the-atp-reports)，您可以使用數個 ATP 報告中的安全性&amp;合規性中心。 (前往**報告** \> **儀表板**。)
  
![安全性&amp;合規性中心的儀表板可協助您查看正常進階威脅防護](../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
ATP 報告包含下列：
- [威脅防護狀態報告](#threat-protection-status-report)
- [ATP 檔案類型報告](#atp-file-types-report)
- [ATP 郵件處置報告](#atp-message-disposition-report)
- [即時偵測或檔案總管]](threat-explorer.md) （視您是否具有 Office 365 ATP 方案 1 或 2）
- ...[以及更多](#additional-reports-to-view)。 

閱讀本篇文章以取得 ATP 報告概觀，以及如何使用它們。
  
## <a name="threat-protection-status-report"></a>威脅防護狀態報告

**威脅保護狀態**報表是整合在一起惡意內容和惡意電子郵件偵測並封鎖由[Exchange Online Protection](exchange-online-protection-overview.md) (EOP) 和[Office 365 ATP](office-365-atp.md)的相關資訊的單一檢視。 這份報告可以用來檢視偵測一段時間 （最多為 90 天），並可讓安全性系統管理員識別趨勢或判斷原則是否需要調整。 

報表會提供唯一的電子郵件與惡意內容，例如檔案或網站位址 (Url) 已封鎖的反惡意程式碼引擎、[零時差自動清除 (ZAP)](zero-hour-auto-purge.md)，和 ATP 功能，例如[ATP 安全連結](atp-safe-links.md)， [ATP 安全附件](atp-safe-attachments.md)， [ATP 防網路釣魚功能](atp-anti-phishing.md)彙總的計數。 

篩選並掌握資訊的允許更細微的分類，這份報告中的資訊。 具體而言，是包含*電子郵件 > 釣魚程式*和*電子郵件 > 惡意程式碼檢視*'細分由' 功能表。 它會細分資料匯入：

| |  |
|---------|---------|
|依偵測類型    | 哪些原則有助於捕捉這些威脅？         |
|偵測技術     | 查看基礎 Microsoft 技術攔截威脅？        |
|依傳遞狀態     | 偵測潛在威脅為電子郵件發生了什麼事？         |
| | |

> [!TIP]
> 電子郵件 > Phish |惡意程式碼檢視有顯示，如*ATP 產生檔案信譽*、*檔案爆炸*、 *URL 引爆*、 類別與偵測技術的細微掌握*反詐騙： DMARC 失敗*，例如，指出哪一個功能完全 led 來捕捉威脅組織很有幫助。

![威脅保護狀態報告] 下拉式清單顯示 '細分由'。](../media/tp-threatProtectStatRpt-BreakDownBy.png)

這些檢視提供您選項來匯出，透過按一下按鈕 （在電子郵件 > 釣魚程式、 電子郵件 > 惡意程式碼、 和內容 > 惡意程式碼檢視）。 彙總的資料匯出到您的電腦可以在 Excel 中開啟。

![此圖形顯示匯出為惡意程式碼的右之間建立排程] 及 [要求報表檢視] 功能表中的選項。](../media/tp-threatProtectStatRpt-BreakDownByExport.png)

[概觀] 和 [電子郵件檢視會顯示小時內的資訊的處理，而不是在 24 小時 （re 需求。 增加的速度已清除的訊號） ！

> [!NOTE]
> 威脅保護狀態報表是適用於擁有[Office 365 ATP](office-365-atp.md)或[Exchange Online Protection](exchange-online-protection-eop.md) (EOP); 客戶然而，ATP 客戶威脅保護狀態報表中顯示的資訊可能會包含不同資料比 EOP 客戶可能會看到的內容。 例如，ATP 客戶威脅保護狀態報表將包含[SharePoint Online、 OneDrive 或 Microsoft Teams 中偵測到惡意檔案](atp-for-spo-odb-and-teams.md)的相關資訊。 這類資訊是專屬於 ATP，，因此 EOP，但不是 ATP 的客戶將不會看到其威脅保護狀態報表中的這些詳細資料。
  
若要檢視中的威脅保護狀態報表，[安全性&amp;合規性中心](https://protection.office.com)，請移至**報表** \> **儀表板** \> **威脅保護狀態**。
  
![ATP 威脅保護狀態報表](../media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
若要取得一天的詳細的狀態，將游標置於上方圖形。
  
![一天的 ATP 威脅保護狀態資料](../media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
根據預設，威脅保護狀態報告顯示過去 7 天的資料。 不過，您可以選擇 [**篩選器**，並變更日期範圍，以檢視最多為 90 天的資料。 （如果您使用試用訂閱，您可能會受限於的 30 天的資料。）
  
![ATP 威脅保護狀態篩選](../media/4f703369-642b-402b-9758-b9c828283410.png)
  
您也可以使用 [**檢視資料**] 功能表來變更報表中顯示的資訊。 
  
![檢視 ATP 威脅保護狀態報表的選項](../media/4959bf8c-d192-4542-b00b-184e101e7513.png)

## <a name="url-protection-status-report"></a>URL 保護狀態報表

這個報告是根據的資料收集，並偵測到威脅，按一下 [每 （而最其他電子郵件威脅相關報告是每個郵件資料）。 這份報告被設計來顯示來自中電子郵件和文件，每次按一下超連結的威脅。 有兩種檢視：

|  |  |
|---------|---------|
|按一下 [URL 保護巨集指令   | 請參閱 Url 封鎖、 封鎖，但由使用者覆寫點選中的使用者，並允許覆寫點選中的數目。        |
|URL 按一下 [應用程式     | 請參閱從中 URL 已按下的應用程式。        |
|  |  |

在詳細資料表格中，您可以查看更多關於按一下 [時間與使用者資訊。 最後，請記住 URL 保護狀態報告 」 可顯示從 ATP 安全連結功能的保護，只讓已啟用 ATP 安全連結的客戶會看到的資料會反映在這份報告。

> [!NOTE]
> 這是*保護趨勢報告*、 意義的資料代表較大的資料集的趨勢。 報告中不提供以下即時。 按一下 [URL 的即時的資料，請繼續使用 URL 追蹤。

## <a name="atp-file-types-report"></a>ATP 檔案類型報告

**ATP 檔案類型**的報告顯示[ATP 安全附件](atp-safe-attachments.md)所偵測到視為惡意的檔案的類型。
  
若要檢視此報告中，在[安全性&amp;合規性中心](https://protection.office.com)，請移至**報表** \> **儀表板** \> **ATP 檔案類型**。
  
![ATP 檔案類型報告](../media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
當您將游標的特定一天時，您可以看到分解為由[ATP 安全附件](atp-safe-attachments.md)所偵測到的惡意檔案的類型和[反垃圾郵件&amp;Office 365 中的反惡意程式碼保護](anti-spam-and-anti-malware-protection.md)。
  
![一天的 ATP 檔案類型報告資料](../media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a>ATP 郵件處置報告

**ATP 郵件處理**報告會顯示您針對已偵測到具有惡意內容的電子郵件所採取的動作。 
  
若要檢視此報告中，在[安全性&amp;合規性中心](https://protection.office.com)，請移至**報表** \> **儀表板** \> **ATP 郵件處理**。
  
![ATP 郵件處理報告](../media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
當您將滑鼠停留在圖表中的列時，您可以看到哪些動作是偵測到的電子郵件的那一天。
  
![一天的 ATP 郵件處理報告資料](../media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a>若要檢視其他報告

除了本文所述的 ATP 報告下, 表所述，都可以使用、 數個其他報告：

|報告  |詳細資料  |
|---------|---------|
|**檔案總管**] 或 [**即時偵測**（Office 365 ATP 計劃 2 的客戶會有瀏覽器;Office 365 ATP 計劃 1 客戶擁有即時偵測的資訊）。| [威脅總管 (及即時偵測)](threat-explorer.md)       |
|**電子郵件安全性報告**，例如頂端寄件者和收件者報告、 詐騙郵件] 報告和垃圾郵件偵測] 報告。 | [檢視安全性與合規性中心內的電子郵件安全性報告](view-email-security-reports.md)        |
|**ATP 安全連結 URL 追蹤**（這是您藉由使用 PowerShell 產生報表）。這份報告顯示過去七 （7） 天 ATP 安全連結動作的結果。 |[Get-urltrace cmdlet 參照](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-urltrace) |
|（這是您藉由使用 PowerShell 產生自訂報告）**透過 EOP 和 ATP 的結果**。 此報告中包含的資訊，例如網域、 日期、 事件類型、 方向、 巨集指令，以及訊息計數。  | [取得 MailTrafficATPReport cmdlet 參照](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport) |
|**EOP 和 ATP 偵測**（這是您藉由使用 PowerShell 產生自訂報告）。 這份報告包含詳細惡意檔案或 Url、 網路釣魚嘗試、 模擬，以及其他電子郵件或檔案中的潛在威脅。   | [取得 MailDetailATPReport cmdlet 參照](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport)        |

  
## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a>若要檢視 ATP 報告需要哪些權限？

若要檢視及使用本文中所述的報告**您必須具有適當的角色指派給這兩種安全性&amp;規範中心和 Exchange 系統管理中心**。

- 針對「安全性與合規性中心」，您必須受指派下列其中一個角色：
    - 組織管理
    - 安全性系統管理員 (這可以在 Azure Active Directory 系統管理中心指派 ([https://aad.portal.azure.com](https://aad.portal.azure.com)))
    - 安全性讀取者

- 針對 Exchange Online，您必須在 Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) 或 PowerShell Cmdlet (請參閱 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)) 受指派下列其中一個角色：
    - 組織管理
    - 僅檢視組織管理
    - 僅檢視收件者角色
    - 合規性管理

若要深入了解，請參閱下列資源：

- [Office 365 安全性與合規性中心權限](permissions-in-the-security-and-compliance-center.md)

- [Exchange Online 中的功能權限](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
## <a name="what-if-the-reports-arent-showing-data"></a>如果報表不顯示資料？

如果您不 ATP 報告中看到的資料，請仔細檢查您的原則已正確設定。 您的組織必須有[ATP 安全連結原則](set-up-atp-safe-links-policies.md)，並定義 ATP 保護的順序中的[ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)就地。 請參閱[在 Office 365 中的反垃圾郵件和反惡意程式碼保護](anti-spam-and-anti-malware-protection.md)。
  
## <a name="related-topics"></a>相關主題

[報告和 Office 365 安全性的深入解析&amp;合規性中心](reports-and-insights-in-security-and-compliance.md)
  
[建立報表排程安全性&amp;合規性中心](create-a-schedule-for-a-report.md)
  
[設定及下載自訂報告中的安全性&amp;合規性中心](set-up-and-download-a-custom-report.md)
  

