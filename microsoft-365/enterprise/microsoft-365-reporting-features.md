---
title: Microsoft 365 報告功能
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-analytics
f1.keywords:
- NOCSH
description: 深入瞭解 Microsoft 365 內的各種報告功能，包括 Azure Active Directory 和 Exchange Online。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3beb327bd5cb995c378a414e19cc54dea8ad1304
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332733"
---
# <a name="microsoft-365-reporting-features"></a>Microsoft 365 報告功能

Microsoft 365 中的報表功能提供各種針對 Azure Active Directory (Azure AD) 、Exchange Online、裝置管理、監察檢查和資料遺失防護 (DLP) 的審計報告。 這些報告與 Microsoft 365 活動報告不同，彼此分開。

## <a name="microsoft-365-reports-dashboard"></a>Microsoft 365 報告儀表板

Microsoft 365 系統管理中心預覽中的 [報告] 儀表板會顯示跨 Microsoft 365 的使用狀況活動。 Microsoft 365 全域管理員或 Exchange Online、SharePoint 線上或商務用 Skype 系統管理員，可以深入瞭解服務的使用狀況。 例如，在特定 Microsoft 365 服務中的使用者人數，已啟用先前命名為 Office 365 ProPlus) 的 Microsoft 365 應用 (程式的使用者數目，以及郵件在組織中流動的程度。 報告可用於過去7、30、90和180天。

您可以使用下列報告：

- [電子郵件活動報告](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--Email-activity-1cbe2c00-ca65-4fb9-9663-1bbfa58ebe44)
- [Microsoft Office 啟用報告](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--Microsoft-Office-activations-87c24ae2-82e0-4d1e-be01-c3bcc3f18c60)
- [SharePoint 線上網站使用量報告](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--SharePoint-site-usage-4ecfb843-e5d5-464d-8bf6-7ed512a9b213)
- [商務流量報告 OneDrive](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Preview--OneDrive-for-Business-usage-0de3b312-c4e8-4e4b-a02d-32b2f726a680)
- [Yammer 活動報告](https://support.office.com/article/View-the-Yammer-Activity-report-in-the-Office-365-admin-center-preview-c7c9f938-5b8e-4d52-b1a2-c7c32cb2312a)
- [商務用 Skype 活動報告](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/activity-report)
- [商務用 Skype Peer-to-Peer 活動報告](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/peer-to-peer-activity-report)
- [商務用 Skype 會議召集人報告](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/conference-organizer-activity-report)
- [商務用 Skype 會議參與者活動報告](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/conference-participant-activity-report)

如需詳細資訊，請參閱 [Microsoft 365 系統管理中心的活動報告](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)。

## <a name="azure-ad-reports"></a>Azure AD 報告

Microsoft 365 使用 Azure AD 進行驗證和身分識別管理。 Microsoft 365 系統管理員會使用 Azure 所產生的報告，識別不尋常的活動，並對其資料進行未經授權的存取。 您可以在 Azure AD 中使用 access 和使用方式報告，以深入瞭解您組織的目錄完整性及安全性。 使用此資訊，您可以找出並緩解可能的安全性風險。

Azure AD 報告可以匯出至 Microsoft Excel，並與 Microsoft 365 中的其他資料相關聯。 例如，審核記錄搜尋的結果可讓您瞭解存取、驗證及應用層級的活動。 您可以使用 Azure AD Premium 的高級反常和資源使用狀況報告。 這些高級報告可協助您改善安全性狀況，並透過應用裝置存取和應用程式使用方式的分析來協助您回應潛在威脅。 如需詳細資訊，請參閱 [Azure Active Directory 報告](https://docs.microsoft.com/azure/active-directory/reports-monitoring/overview-reports/)。

## <a name="exchange-online-audit-reports"></a>Exchange Online 審核報告

Exchange Online 審核報告包含信箱存取的詳細資料，以及系統管理員對您的 Exchange Online 租使用者所做的變更。 透過信箱審核，您可以使用下表中的工作執行報告及匯出 Exchange Online 審核記錄。

> [!NOTE]
> 您必須啟用每個信箱的信箱審核記錄，以便在該信箱的審計記錄中儲存已審核的事件。 如果信箱審核記錄未啟用信箱，該信箱的事件將不會儲存在審計記錄檔中，也不會出現在信箱審計報告中。 如需詳細資訊，請參閱 [啟用信箱審核](https://support.office.com/article/Enable-mailbox-auditing-in-Office-365-aaca8987-5b62-458b-9882-c28476a66918)。

| 工作 | 說明 |
|----------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [執行非擁有者信箱存取報告](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report) | 顯示其他人員存取的信箱清單，而非信箱的擁有者。 報告包含誰存取信箱的相關資訊、他們在信箱中採取的動作，以及動作是否成功。 |
| [匯出信箱稽核記錄](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs) | 信箱審核記錄檔包含信箱擁有者以外的使用者所採取之信箱中存取和動作的資訊。 管理員可以指定信箱，並在日期範圍內產生報告。 這些記錄會以 XML 形式匯出，並附加至郵件，並傳送給特定使用者，如系統管理員所決定。 |
| [執行系統管理員角色群組報告](https://docs.microsoft.com/Office365/SecurityCompliance/eop/run-an-administrator-role-group-report-in-eop-eop) | 系統管理員角色群組會指派系統管理許可權給使用者。 這些許可權可讓使用者執行系統管理工作，例如重設密碼、建立或修改信箱，以及將系統管理員許可權指派給其他使用者。 系統管理員角色群組報告會顯示對角色群組所做的變更，包括新增或移除成員。 |
| [查看系統管理員審核記錄檔](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log) | 系統管理員審核記錄報告會列出系統管理員在 Exchange Online 中所執行的所有建立、更新和刪除功能。 記錄專案提供已執行 Cmdlet 的資訊、使用的參數、執行 Cmdlet 的執行者，以及受影響的物件。 |
| [信箱內容搜尋和保留](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) | 提供 In-Place eDiscovery 或信箱上 In-Place 保留設定之任何變更的詳細資料。 |
| [匯出系統管理員審核記錄檔](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/search-role-group-changes) | 系統管理員審核記錄檔會記錄在 Exchange Online 中建立、更新和刪除等特定的管理動作。 記錄的結果會匯出為 XML，管理員可以選擇將此記錄傳送給一組使用者。 |
| [執行每個信箱的訴訟資料暫留報告](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/per-mailbox-litigation-hold-report) | 提供信箱的訴訟暫止設定變更的詳細資料。 |
| [查看和匯出外部系統管理員審核記錄](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-external-admin-audit-log) | 包含外部管理員執行之動作的詳細資料。 這些專案會提供已執行 Cmdlet 的資訊、所使用的參數，以及在 Exchange Online 中建立、修改或刪除物件的任何動作。 |

## <a name="device-compliance-reports"></a>裝置合規性報告

您可以使用 Microsoft 365 行動裝置管理 (MDM) ，管理和保護連線至您訂閱的行動裝置。 用來存取工作電子郵件、行事曆、連絡人及檔的行動裝置，可確保員工可以隨時隨地運作，並在任何地方運作。 保護貴組織的資訊非常重要。 您可以使用 Microsoft 365 MDM 設定裝置安全性原則和存取規則。 如果遺失或遭盜，您也可以使用 Microsoft 365 MDM 來清除行動裝置。

MDM 相容性報告可提供組織設定的原則，以保護存取 Microsoft 365 資料的行動裝置。 報告允許依照相容性狀態、報告的違規、封鎖的裝置，以及由於安全性原則所擦除的裝置，來篩選裝置。 如需詳細資訊，請參閱 [Microsoft 365 行動裝置管理的概述](https://support.microsoft.com/office/overview-of-mobile-device-management-mdm-for-microsoft-365-faa7d8e5-645d-4d59-839c-c8d4c1869e4a)。

## <a name="data-loss-prevention"></a>資料外洩防護

DLP 原則可協助管理組織中資訊的安全性和流程。 您可以設定原則，以封鎖存取內容、加密資料，或使用隨應用程式中的 DLP 原則提示來通知使用者原則及原則違規。 DLP 報告可提供原則和規則相符專案、覆寫和誤報的洞察力。

您可以使用 Microsoft 365 系統管理中心，查看 DLP 原則所偵測到的郵件數目資訊。 DLP 報告可提供傳送和接收郵件的原則和規則相符專案的見解。 您也可以使用 Exchange 系統管理中心，查看過去24小時內每個原則的相符、覆寫和誤報數目。 如果您下載 Excel 報告，您可以查看更多詳細資料，例如誰傳送哪一封郵件、哪一天，以及哪些原則相符已觸發。 如需詳細資訊，請參閱 [查看有關 DLP 原則](https://docs.microsoft.com/previous-versions/exchange-server/exchange-150/jj889415(v=exchg.150))偵測的報告。

## <a name="auditing-in-yammer-enterprise"></a>Yammer Enterprise 中的審計

Yammer Enterprise 可讓系統管理員透過 [yammer 資料匯出 API](https://support.office.com/article/export-data-from-yammer-enterprise-b303d8f3-007d-4ad4-81f8-54fb1ecfb3f2)從其 Yammer 網路匯出使用者活動資料，或透過 yammer 網路管理頁面手動進行。 將記錄匯出的功能限制為 Yammer 中的網路系統管理員。  (所有 Microsoft 365 全域系統管理員皆為 Yammer 網路系統管理員。 ) 

可匯出的資料如下：

| Filename | 說明 |
|----------------------------|-------------------------------------------------------------------------|
| Users.csv | 網路中所有的新、擱置和擱置的使用者 |
| Messages.csv | 網路中的所有郵件 |
| Files.csv (中繼資料)  | 中繼資料，例如 filename、檔案 API URL、上載載入識別碼、上傳的位置等等。 |
| Files.csv (原始檔案)  | 使用者在 Yammer 中上傳原始檔案的 Zip 檔案 |
| Topics.csv | 在網路上建立的主題 |
| Pages.csv | 網路中使用者所建立的頁面 (記事)  |
| Admins.csv | 網路上所有已驗證的系統管理員 |
| Networks.csv | 所有 Yammer 外部網路 |

Yammer Enterprise 資料也可透過 Microsoft 365 活動報告取得。 此外，Yammer 正積極運作透過 Microsoft 365 管理活動 API 公開其他記錄，以及透過使用 Power BI 的資料進行原因。 如需這些功能的詳細資訊，請參閱 [Office 藍圖](https://fasttrack.microsoft.com/roadmap?filters=yammer) 。
