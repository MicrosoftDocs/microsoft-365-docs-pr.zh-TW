---
title: 在新的德國資料中心區域遷移至 Office 365 服務之後，會有什麼變更？
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: 摘要：瞭解已變更，以從 microsoft 雲端德國移動 (microsoft cloud Deutschland) 以 Office 365 新德文 datacenter 區域中的服務。
ms.openlocfilehash: e503df16cfdbe0985e635b07cb6b4a45bc55d367
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930400"
---
# <a name="what-will-change-after-the-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>在新的德國資料中心區域遷移至 Office 365 服務之後，會有什麼變更？

承租人遷移的設計是要對管理員和使用者造成最小影響。 不過，每個工作負載都有需要考慮的事項。 請參閱下列各節，以更深入瞭解工作負載的遷移經驗。

以下是 Microsoft Cloud Deutschland and new 德文 datacenter 地區的 Office 365 服務之間的主要差異。

| 類別 | Microsoft Cloud Germany (Microsoft Cloud Deutschland) | 新德國資料中心區域中的 Office 365 服務 |
|:-------|:-----|:-------|
| Microsoft 365 服務可供訂閱，且只有一個 Office 365 租用戶 | 15個服務 | 29個服務 <br><br> 如需詳細資訊，請參閱[不同的 Office 365 雲端服務選項之間的服務可用性為何？](ms-cloud-germany-transition.md#serv-avail)。 |
| 新功能 | 將不會提供任何新功能。 | 新功能將可與 Office 365 服務一致。 |
| 資料信任者 | 是 | 否 |
| 與全球 Office 365 租用戶的跨租用戶共同作業 | 否 | 是 |
| 客戶資料存留處 | 客戶資料只會儲存在德國資料中心內。 | Microsoft 會以獨佔方式在德國存放下列客戶資料： <ul><li> Exchange Online 信箱內容 (電子郵件內文、行事曆專案和電子郵件附件的內容)  </li><li> SharePoint線上網站內容和儲存在該網站中的檔案，以及上傳至商務用 OneDrive 的檔案 </li></ul> |
| 適用條款 | 含此項[補充](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=64)的[線上服務條款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) | [線上服務條款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) |
||||

## <a name="azure-active-directory"></a>Azure Active Directory

什麼不會變更：

- 租使用者初始網域 (例如 `contoso.onmicrosoft.de` 包含租使用者識別碼 (GUID) 和自訂網域的) 會在遷移之後保留。 

- 遷移至 Office 365 服務之資源的驗證要求是由 Office 365 服務 Azure 驗證服務 () 所授 `login.microsoftonline.com` 。 在遷移期間，仍然位於 Office 365 德國的資源會由現有的德國 Azure 服務 () 進行驗證 `login.microsoftonline.de` 。

注意事項附注：

- 針對受管理的網域帳戶，在複製初始 Azure Active Directory (Azure ad) 租使用者完成之後 (是 azure ad 遷移至 Office 365 服務 Azure ad 服務) 的第一步，密碼變更、自助密碼重設 (SSPR) 變更和密碼重設，必須從 Office 365 服務入口網站完成。 從德國服務更新密碼的要求無法在此時刻成功，因為 Azure AD 租使用者已遷移至 Office 365 服務。 重設同盟網域密碼不會受到影響，因為這些密碼在內部部署目錄中已完成。

- Azure 登入是在使用者嘗試存取的入口網站中呈現。 在轉換後，只可從 Office 365 服務端點取得審核記錄。 在遷移完成之前，應從 Microsoft Cloud Deutschland 入口網站儲存登入和審核記錄。

- 密碼重設、密碼變更、受管理組織的系統管理員未使用 Active Directory Federation Services (的密碼) 必須透過 Office 365 服務入口網站來執行。 存取 Microsoft Cloud Deutschland 入口網站重設密碼的使用者嘗試將會失敗。

- 一般資料保護法規 (GDPR) 資料主體要求 (dsr) 會從 Office 365 服務 Azure admin 入口網站執行，以進行未來的要求。 在 Microsoft 雲端 Deutschland 中的任何舊版或非客戶診斷資料會在30天內刪除。

## <a name="subscriptions--licenses"></a>訂閱 & 授權

- Microsoft Cloud Deutschland 的 Office 365 和 Dynamics 訂閱會透過 Azure AD 重新安置轉換為德文地區。 然後會更新組織，以反映新的 Office 365 服務訂閱。 在 brief 訂閱傳輸過程中，會封鎖對訂閱所做的變更。

- 當租使用者轉換成 Office 365 服務時，其德國特定訂閱和授權會以新的 Office 365 服務產品進行標準化。 對應的 Office 365 服務訂閱會為轉接的德國訂閱進行購買。 具有德國授權的使用者將被指派 Office 365 服務授權。 完成後，舊版的德國訂閱會取消，並從目前的 Office 365 服務租使用者中移除。

- 在遷移個別工作負載後，會透過 Office 365 服務 (如 Microsoft Planner 和 Microsoft Flow) 等其他功能，因為有新的 Office 365 服務訂閱。 如果適用于您的組織，租使用者或授權管理員可以在您規劃變更管理以引進新服務時，停用新的服務方案。 如需如何停用指派給使用者授權之服務方案的指引，請參閱[在指派使用者授權時停用 Microsoft 365 服務的存取權](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)。

## <a name="exchange-online"></a>Exchange Online

- Exchange 資源 URLs 在遷移之後從舊版德國端點轉換 `outlook.office.de` 至 Office 365 服務端點 `outlook.office365.com` 。 在遷移完成之前，您的使用者可能會使用舊版 URL 存取其已遷移的信箱。 客戶在 Exchange 遷移後，應儘快將使用者轉換至新的 URL，以避免對德國環境的退休影響。 Outlook 服務的 Office 365 服務 URLs 只會在 Exchange 遷移開始之後才可用。

- 信箱會遷移成後端程式。 您組織中的使用者可能會在轉換期間的 Microsoft 雲端 Deutschland 或德國地區內，且屬於相同的全域通訊清單) 中相同 Exchange 組織 (的一部分。

- 使用信箱所在之 URL 存取服務的 Outlook Web App 使用者，將會看到額外的驗證提示。 例如，如果使用者的信箱位於 Office 365 服務，而且使用者的 Outlook Web App 連線使用舊版端點 `outlook.office.de` ，使用者會先驗證 `login.microsoftonline.de` ，然後再驗證至 `login.microsoftonline.com` 。 遷移完成時，使用者可以 () 存取新的 URL `https://outlook.office365.com` ，而且他們只會看到單一、預期的登入要求。 

## <a name="sharepoint-online"></a>SharePoint Online

在 SharePoint 線上及商務用 OneDrive 中，您可以透過 Outlook 共用專案。 按 Outlook 按鈕之後，會建立可共用的連結，並將其推入 Outlook Web App 中的新郵件。

在完成 SharePoint 線上的遷移之後，透過 Outlook 中的 SharePoint 線上及商務用 OneDrive 中共用專案已不再運作。 我們承認這是已知的問題。 不過，由於此 Outlook 功能位於棄用的路徑中，因此在完成棄用之前，不會規劃修正問題。

## <a name="office-services"></a>Office服務

Office線上服務可透過 `office.de` 過渡前後進行存取。 將使用者的信箱轉換為 Office 365 服務後，使用者應開始使用 Office 365 服務 URLs。 當後續工作負載遷移至 Office 365 服務，office.com 入口網站的介面就會開始運作。

Office 的最近使用 (MRU) 服務，是從 Microsoft Cloud Deutschland 轉換為 Office 365 全域服務，而非遷移。 從 Office .com 入口網站遷移後，只會顯示來自 Office 365 泛型服務端的 MRU 連結。 來自 Microsoft Cloud Deutschland 的 mru 連結不會顯示為 Office 365 泛型服務中的 mru 連結。 在 Office 365 泛型服務中，只有在租使用者遷移到達階段9之後，才能存取 MRU 連結。

## <a name="exchange-online-protection"></a>Exchange Online Protection

- 後端 Exchange Online Protection (EOP) 功能會複製到新的德國地區。
- Office 365安全性與合規性中心使用者必須在遷移時轉換為使用全域 URLs `https://protection.office.com` 。

## <a name="skype-for-business-online"></a>商務用 Skype Online

現有的商務用 Skype Online 客戶將會移轉 Microsoft Teams。 如需詳細資訊，請參閱 [https://aka.ms/SkypeToTeams-Home](/microsoftteams/upgrade-start-here) 。

## <a name="office-365-video"></a>Office 365 影片

Office 365影片會在2021年3月1日、及 Office 365 影片中，將 SharePoint 線上遷移至新的德國資料中心區域已完成後，就不會支援。 SharePoint 線上進行遷移時，會將 Office 365 影片的內容遷移。 不過，SharePoint 遷移之後，Office 365 影片中的影片不會在 Office 365 的視頻 UI 中播放。 若要深入瞭解遷移時程表，請參閱[Office 365 影片轉換至 Microsoft Stream (經典) 概述](/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)。

## <a name="next-step"></a>下一步

[瞭解遷移階段的動作和影響](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>其他資訊

開始：

- [從 Microsoft Cloud Deutschland 遷移至新德國資料中心區域的 Office 365 服務](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 移轉協助](https://aka.ms/germanymigrateassist)
- [如何選擇加入移轉](ms-cloud-germany-migration-opt-in.md)

在轉換中移動：

- [移轉階段的動作與影響](ms-cloud-germany-transition-phases.md)
- [其他預備工作](ms-cloud-germany-transition-add-pre-work.md)
- [AZURE AD](ms-cloud-germany-transition-azure-ad.md)、[裝置](ms-cloud-germany-transition-add-devices.md)、[經驗](ms-cloud-germany-transition-add-experience.md)和[AD FS](ms-cloud-germany-transition-add-adfs.md)的其他資訊。

雲端應用程式：

- [Dynamics 365 的移轉程式資訊](/dynamics365/get-started/migrate-data-german-region)
- [Power BI 移轉程式資訊](/power-bi/admin/service-admin-migrate-data-germany)
- [開始升級您的 Microsoft Teams](/microsoftteams/upgrade-start-here)
