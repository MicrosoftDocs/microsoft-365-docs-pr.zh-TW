---
title: 為 Microsoft 受管理的電腦準備對應磁碟機
description: 重要步驟，確定
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: fc216adadea8dd774901d42a754fb288412318a1
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104591"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>為 Microsoft 受管理的電腦準備對應磁碟機

許多企業環境對對應的磁片磁碟機具有舊版需求，以允許其使用者或小組共用及儲存檔案，或用於內部部署應用程式。 Microsoft 不建議搭配 Microsoft Managed Desktop 使用對應的磁片磁碟機。 相反地，我們建議您現代化檔存取解決方案，如下所示：
  
- 將個別使用者所使用的對應磁片磁碟機遷移至 OneDrive 商務。 
- 遷移小組所用的對應磁片磁碟機，以共用檔案至 SharePoint 線上。 
- [現代化] 或 [取代] 任何使用內部部署檔案共用的應用程式，以移除該需求。
  
現代化這些服務可讓 Microsoft 受管理的電腦取得最佳的使用者體驗。 Microsoft FastTrack 服務可協助您使用 Microsoft 雲端服務現代化您的環境。 您可以檢查您是否符合 [合格服務與計畫](https://docs.microsoft.com/fasttrack/m365-eligible-services-and-plans) 的 FastTrack 服務，然後直接與他們聯繫以準備 Microsoft 受管理的電腦。 如需 FastTrack 商務 OneDrive 或 SharePoint 線上遷移的背景，請參閱 [資料移轉](https://docs.microsoft.com/fasttrack/o365-data-migration)。

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>Microsoft 受管理電腦上的對應磁片磁碟機
 
如果您無法移除或取代某些使用案例中的對應磁片磁碟機，您應該提交 Microsoft Managed Desktop admin 入口網站的支援要求，將其部署至 Microsoft 受管理的桌面使用者。
    
針對這類要求，您必須在支援要求中提供下列詳細資料： 

- 必須對應至 Microsoft 受管理的電腦裝置的檔案共用位置的所有 UNC 路徑 
- 需要存取這些檔案共用位置的使用者群組 
- 必要時必須指派 (任何特定的磁碟機號) 

例如：

| 磁碟機號 | UNC 路徑 | 使用者群組 |
|--------------|----------|------------|
| X：  | \\\server\share\Marketing | ContosoMarketing |

您應完全負責確保使用者和群組具有及維護存取檔案共用位置的適當許可權，且內部部署檔案服務仍然可供存取。 此外，您也應該儘快移除這些檔案共用的需求。

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>在 Microsoft 受管理的電腦中部署對應磁片磁碟機
 
請確定無法避免使用對應的磁片磁碟機，而且在提交任何服務要求之前，您已仔細查看需求。 請遵循下列步驟：

1. 流覽至 [ [Microsoft 端點管理員](https://endpoint.microsoft.com/) ]，然後選取 [疑難排解 + 支援]，然後在 [Microsoft Managed Deskop] 區段中尋找「服務要求」。  
2. 提交名為 "對應的磁片磁碟機部署" 的支援要求，並提供所有必要的檔案共用詳細資料。  
3. Microsoft 受管理的桌面 IT 作業會在要求完成時，使用支援要求更新通知。 起初，此設定只會部署至測試部署群組中的裝置。  
4. 您必須測試及確認 Microsoft 受管理的桌面 IT 作業所部署的設定是否如預期的那樣運作。 使用相同支援要求的詳細資料中的 [討論] 索引標籤回復，以在您完成測試時通知 Microsoft 受管理的桌面 IT 作業。  
5. Microsoft 受管理的桌面 IT 作業小組接著會將設定部署至其他部署群組。 
