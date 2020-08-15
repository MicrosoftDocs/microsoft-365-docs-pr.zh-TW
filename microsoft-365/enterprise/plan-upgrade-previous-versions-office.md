---
title: 規劃從 Office 2007 或 2010 伺服器和用戶端升級
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/15/2020
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.assetid: b2acaeca-4986-40f4-92b7-a1bdd06e549d
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: 本文包含使用 Office 2007 或 Office 2010 的使用者的資源，可協助他們規劃升級。
ms.openlocfilehash: 0ad90235bf7ad862a1f0162f87dca7ee2df3d799
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688503"
---
# <a name="plan-your-upgrade-from-office-2007-or-office-2010-servers-and-clients"></a>規劃從 Office 2007 或 Office 2010 伺服器和用戶端升級

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

如果貴組織使用的是舊版 Office 產品和伺服器，現在是開始規劃升級的絕佳時機。 Office 2007 產品和服務已[終止支援](upgrade-from-office-2007-servers-and-products.md)。 

- Office 2010 和 Exchange 2010 將于 **2020年10月13日** 終止支援。 
- SharePoint 2010 和 Project Server 2010 將於 **2021 年 4月 13日**終止支援。 

請使用本文中的資源開始著手。

如需詳細資料，請參閱[從 Office 2010 伺服器和用戶端升級](upgrade-from-office-2010-servers-and-products.md)。

## <a name="what-is-microsoft-365"></a>什麼是 Microsoft 365？

[Microsoft 365](https://www.microsoft.com/microsoft-365) 是創新的 Office 應用程式、智慧雲端服務和世界類別安全性的組合，其設計目的是協助您進一步實現。

Microsoft 365 包含授權和功能，可協助確保您的組織在最新的 Windows 作業系統上運作，而且您的裝置（包括 Windows、iOS 和 Android）已使用需要驗證和資料保護的原則進行註冊並保持安全。 此外，Windows 10 和您的 Microsoft 365 應用程式 enterprise (先前名為 Office 365 ProPlus) 用戶端軟體會繼續更新，以包含最新的功能和安全性更新。
  
Microsoft 365 是一種由 Microsoft 雲端提供及保護，且具備不斷改善的裝置和生產力體驗的數位商務轉換方式。
  
|**資源**|**描述**|
|:-----|:-----|
|[Microsoft 365](https://www.microsoft.com/microsoft-365) <br/> |取得不同 Microsoft 365 版本的相關資訊。  <br/> |
|[Microsoft 365 商務版文件](https://docs.microsoft.com/microsoft-365/business/) <br/> |取得適用於中小企業的 Microsoft 365 版本的詳細資訊。  <br/> |
|[Microsoft 365 教育版文件](https://docs.microsoft.com/microsoft-365/education/) <br/> |取得適用於教育組織的 Microsoft 365 版本的詳細資訊。  <br/> |
|[Microsoft 365 企業版文件](https://docs.microsoft.com/microsoft-365/enterprise/) <br/> |取得適用於企業組織的 Microsoft 365 版本的詳細資訊。  <br/> |

## <a name="what-happens-if-i-dont-upgrade"></a>如果我不升級，會發生什麼事？

您可以選擇不要在這時候升級， 內部部署伺服器和應用程式皆會繼續執行。 不過，當您不再收到安全性更新或支援選項時，您或貴組織可能容易受到安全性漏洞的影響。 我們強烈建議您儘快規劃升級，不論是 Microsoft 365 或更新的內部部署伺服器和應用程式版本。

## <a name="what-upgrade-options-are-available"></a>有哪些升級選擇？      

組織可考慮數個選擇：

- **升級您的內部部署伺服器和應用程式。** 如果使用內部部署 Office 產品和伺服器應用程式，請參閱下列規劃內容：<br/> 

    
    |Office 2007 產品和服務  |Office 2010 產品和服務  |
    |---------|---------|
    |[Office 2007](https://docs.microsoft.com/DeployOffice/office-2007-end-support-roadmap) (桌面) | [Office 2010](https://docs.microsoft.com/DeployOffice/office-2010-end-support-roadmap) (桌面) |
    |[Exchange 2007](exchange-2007-end-of-support.md) |[Exchange 2010](exchange-2010-end-of-support.md) |
    |[SharePoint 2007](sharepoint-2007-end-of-support.md) |[SharePoint 2010](upgrade-from-sharepoint-2010.md) |
    |[Office Communications Server](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/upgrade) |[Lync Server 2010](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/upgrade) |
    |[Project Server 2007](project-server-2007-end-of-support.md) |[Project Server 2010](project-server-2010-end-of-support.md) |
    |[PerformancePoint Server 2007](pps-2007-end-of-support.md) | |
 
- **使用 Microsoft 365 或 Office 365 來執行混合式解決方案。** 混合式解決方案使用您的內部部署伺服器和應用程式，以及其同等雲端伺服器和應用程式。 如果您是分階段移至雲端，或必須保留一些內部部署伺服器和應用程式，則混合式解決方案可能適合貴組織。 如需詳細資料，請參閱 [Microsoft cloud for enterprise 架構師圖例](../solutions/cloud-architecture-models.md) 。 
    
- **使用 Microsoft 365 或 Office 365 移至雲端。** 對許多客戶來說，移至雲端是有效率且符合成本效益的解決方案。 透過完全移至雲端，設定及持續管理會更容易，而且您可以順暢地取得所有最新的功能和安全性更新。 如需更多資訊，請參閱本文的[什麼是 Microsoft 365？](#what-is-microsoft-365)
    
### <a name="help-is-available-for-your-organization"></a>貴組織可取得協助

如需規劃升級的協助，請考慮下列其中一或多個選擇：

- 與合作夥伴或大量授權專家合作。 [尋找您的 Microsoft 365 合作夥伴或轉銷商](https://support.office.com/article/b6c18a9b-2aed-4c84-9d75-af709160258c.aspx)。 

- 如果您的組織購買了特定數目的 Microsoft 365 授權，我們的 FastTrack 小組可協助您完成設定程式。 若要深入瞭解，請參閱 [FastTrack For Microsoft 365](https://www.microsoft.com/fasttrack/microsoft-365)。

- 如果您是小型組織的一部分，或是您想要自行處理組織的 Office 升級，請參閱將 [您的 Microsoft 365 for business 使用者升級至最新的 office 用戶端](https://docs.microsoft.com/office365/admin/setup/upgrade-users-to-latest-office-client)。 
  
## <a name="im-a-home-user-what-do-i-do"></a>我是家用版的使用者。 我該怎麼辦？

如果您使用家用版 Office 2007 或 Office 2010，請考慮下列更新選擇：

- **免費使用瀏覽器中的 Office。** 您可以在瀏覽器中建立、檢視及編輯 Office 檔案，也可以從任何可存取網際網路的裝置存取這些檔案。 [Office 網頁版](https://products.office.com/office-online/documents-spreadsheets-presentations-office-online)包括 [Word 網頁版](https://go.microsoft.com/fwlink/p/?linkid=746664)、[Excel 網頁版](https://go.microsoft.com/fwlink/p/?linkid=746665)、[PowerPoint 網頁版](https://go.microsoft.com/fwlink/p/?linkid=746666)、[OneNote 網頁版](https://go.microsoft.com/fwlink/p/?linkid=746674)、[Sway](https://go.microsoft.com/fwlink/p/?linkid=746675)、[電子郵件](https://go.microsoft.com/fwlink/p/?linkid=746676)、[行事曆](https://go.microsoft.com/fwlink/p/?linkid=746678) 和 [OneDrive](https://go.microsoft.com/fwlink/p/?linkid=746679)。 若要開始使用，請造訪 [office.com](https://office.com)，並使用您的 [Microsoft 帳戶](https://account.microsoft.com/account)登入。 (如果您還沒有 Microsoft 帳戶，可以在 [office.com](https://office.com) 建立一個。)

- **請試用 Microsoft 365，供家用使用。** 使用 [Microsoft 365 系列家庭](https://www.microsoft.com/microsoft-365/p/microsoft-365-family/cfq7ttc0k5dm?rtc=2&activetab=pivot:overviewtab) 版。 開始試用版，查看 Microsoft 365 系列如何適合您運作。 使用 Microsoft 365 系列時，您將享有 OneDrive 的雲端儲存空間。

   由於 [Windows 7 將於 2020 年 1 月 14 日終止支援](https://www.microsoft.com/windowsforbusiness/end-of-windows-7-support)，在 Windows 7 裝置上執行的 Office 365 家用版或 Office 365 個人版提供的 Word、Excel、PowerPoint、Outlook、Publisher 和 Access版本會收到安全性更新，但不會收到功能更新。 若要繼續接收這些應用程式的功能更新，請[將 Windows 7 裝置升級為 Windows 10](https://support.microsoft.com/help/12435/windows-10-upgrade-faq)。
    
- **購買 Office 家用版 &amp; 學生版。** 如果您選擇此選項，便會在您的 Windows 電腦或 Mac 上一次購買 Office。 這不是訂閱，而是提供一部電腦的一次性永久使用授權。 請檢視[需求](https://office.com/systemrequirements)，然後選擇您要使用的版本。

    - 如果您的 Windows 電腦執行 Windows 10，請考慮取得 [Office 家用及學生版 2019](https://www.microsoft.com/p/office-home-student-2019/cfq7ttc0k7c8)。

    - 如果您的 Windows 電腦執行 Windows 7、8或 8.1，而目前未升級為 Windows 10，請考慮從授權轉銷商取得 Office 家用版及學生版 2016 (或其他 Microsoft Office 版本)。
     
     - Windows 7 的支援已 [于2020年1月14日結束](https://www.microsoft.com/windowsforbusiness/end-of-windows-7-support)，但 Microsoft 將不會提供安全性更新或支援。 請將 Windows 7 裝置升級為 Windows 10，以取得持續的安全性和功能更新及後續支援。

您也可以選擇不要在這時候升級， 您的 Office 應用程式將繼續執行。 您可以在[這裡](https://go.microsoft.com/fwlink/p/?linkid=2085724)取得 Office 支援日期的時間表。 不過，升級能提供您安全性更新或新增功能與改良功能。
   
## <a name="next-step"></a>下一步

[從 Office 2007 伺服器與用戶端升級](upgrade-from-office-2007-servers-and-products.md)

或

[從 Office 2010 伺服器與用戶端升級](upgrade-from-office-2010-servers-and-products.md)
   
## <a name="related-topics"></a>相關主題
  
[Microsoft 週期原則](https://go.microsoft.com/fwlink/?linkid=865200)
