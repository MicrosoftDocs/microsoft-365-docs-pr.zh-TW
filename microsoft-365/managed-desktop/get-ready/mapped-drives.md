---
title: 為 Microsoft 受管理的電腦準備對應磁碟機
description: 確定使用者可以存取對應磁片磁碟機上之資料的重要步驟
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: f770f5083fe9193660b03e7971b09a127f2dae16
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574556"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>為 Microsoft 受管理的電腦準備對應磁碟機

許多企業環境對對應的磁片磁碟機具有舊版需求，以允許其使用者或小組共用及儲存檔案，或用於內部部署應用程式。 Microsoft 不建議搭配 Microsoft 受管理的電腦使用對應的磁片磁碟機。 相反地，我們建議您現代化檔存取解決方案，如下所示：
  
- 將個別使用者所使用的對應磁片磁碟機遷移至商務用 OneDrive。 
- 遷移小組所用的對應磁片磁碟機，以共用檔案至 SharePoint 線上。 
- [現代化] 或 [取代] 任何使用內部部署檔案共用的應用程式，以移除該需求。
  
現代化這些服務可讓您使用 Microsoft 受管理的電腦的最佳使用者體驗。 Microsoft FastTrack 服務可協助您使用 Microsoft 雲端服務現代化您的環境。 您可以檢查您是否符合[合格服務與計畫](/fasttrack/m365-eligible-services-and-plans)的 FastTrack 服務，然後直接與他們聯繫以準備 Microsoft 受管理的電腦。 如需 FastTrack 商務用 OneDrive 或 SharePoint 線上遷移的背景，請參閱[資料移轉](/fasttrack/o365-data-migration)。

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>Microsoft 受管理的電腦上的對應磁片磁碟機
 
如果您無法移除或取代某些使用案例的對應磁片磁碟機，您應該在 Microsoft 受管理的電腦系統管理入口網站中提交支援要求，以將其部署至 Microsoft 受管理的電腦使用者。
    
針對這類要求，您必須在支援要求中提供下列詳細資料： 

- 需要為 Microsoft 受管理的電腦裝置對應之檔案共用位置的所有 UNC 路徑 
- 需要存取這些檔案共用位置的使用者群組 
- 必要時必須指派 (任何特定的磁碟機號) 

例如：

| 磁碟機號 | UNC 路徑 | 使用者群組 |
|--------------|----------|------------|
| X：  | \\\server\share\Marketing | ContosoMarketing |

您應完全負責確保使用者和群組具有及維護存取檔案共用位置的適當許可權，且內部部署檔案服務仍然可供存取。 此外，您也應該儘快移除這些檔案共用的需求。

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>在 Microsoft 受管理的電腦中部署對應的磁片磁碟機
 
請確定無法避免使用對應的磁片磁碟機，而且在提交任何服務要求之前，您已仔細查看需求。 請遵循下列步驟：

1. 流覽至[Microsoft 端點管理員](https://endpoint.microsoft.com/)，然後選取「疑難排解 + 支援」，然後尋找 Microsoft 受管理的電腦區段下的「服務要求」。  
2. 提交名為 "對應的磁片磁碟機部署" 的支援要求，並提供所有必要的檔案共用詳細資料。  
3. Microsoft 受管理的電腦完成要求後，IT 作業將會使用支援要求更新通知。 起初，此設定只會部署至測試部署群組中的裝置。  
4. 您必須測試及確認 Microsoft 受管理的電腦的 IT 作業所部署的設定是否如預期的那樣運作。 使用相同支援要求的詳細資料中的 [討論] 索引標籤來回複，以在您完成測試時通知 Microsoft 受管理的電腦的 IT 作業。  
5. Microsoft 受管理的電腦IT 作業小組接著會將設定部署至其他部署群組。 

## <a name="steps-to-get-ready"></a>準備就緒的步驟

1. 審查[Microsoft 受管理的電腦的必要條件](prerequisites.md)。
2. [使用準備工作評估工具](readiness-assessment-tool.md)。
3. [來賓帳戶的先決條件](guest-accounts.md)
4. [Microsoft 受管理的電腦的網路設定](network.md)
5. [為 Microsoft 受管理的電腦準備認證和網路設定檔](certs-wifi-lan.md)
6. [為 Microsoft 受管理的電腦準備內部部署資源存取](authentication.md)
7. [Microsoft 受管理的電腦中的應用程式](apps.md)
8. [準備 Microsoft 受管理的電腦 (本文的對應磁片磁碟機](mapped-drives.md)) 
9. [為 Microsoft 受管理的電腦準備列印資源](printing.md)
