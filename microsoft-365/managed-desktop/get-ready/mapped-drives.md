---
title: 為 Microsoft 受管理的電腦準備對應磁碟機
description: 若要確定重要步驟
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation, Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 8bdbbefb1fc3bfff324787eedb497afe781184f0
ms.sourcegitcommit: 6d672eb8287526a9db90df5fa85bc4984a7047d1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2020
ms.locfileid: "42280171"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>為 Microsoft 受管理的電腦準備對應磁碟機

許多企業環境有舊版的需求，以允許共用及儲存檔案，其使用者或小組的對應磁碟機或內部部署應用程式。 Microsoft 不建議使用對應的磁碟機與 Microsoft 受管理的電腦。 相反地，我們建議您現代化 yor 檔案存取解決方案，如下所示：
  
- 移轉商務用 onedrive 的個別使用者所使用的對應磁碟機。 
- 移轉小組用來共用檔案至 SharePoint Online 的對應磁碟機。 
- 現代化或取代任何應用程式，用於內部部署檔案共用移除此需求。
  
現代化這些服務會允許與 Microsoft 受管理電腦的最佳使用者經驗。 Microsoft FastTrack 服務可以協助您使用 Microsoft 雲端服務現代化您的環境。 您可以檢查您是否是合格的 FastTrack 服務[合格服務與計劃](https://docs.microsoft.com/fasttrack/m365-eligible-services-and-plans)，而且再連絡這些直接向 Microsoft 受管理電腦的準備。 背景 FastTrack 商務用 OneDrive 或 SharePoint Online 移轉資訊，請參閱[資料移轉](https://docs.microsoft.com/fasttrack/o365-data-migration)。

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>Microsoft 受管理的電腦上的對應磁碟機
 
如果您不能移除或取代某些對應磁碟機使用情況下，您應該提交 Microsoft 受管理的電腦系統管理入口網站中的支援要求，已將其部署至 Microsoft 受管理電腦的使用者。
    
這類要求，您必須提供支援要求中的下列詳細資料： 

- 所有的 UNC 路徑，檔案共用必須要對應的 Microsoft 受管理的電腦裝置的位置 
- 需要這些檔案共用位置的存取權的使用者群組 
- （如果需要） 分派需要任何特定的磁碟機代號

例如：

| 磁碟機代號 | UNC 路徑 | 使用者群組 |
|--------------|----------|------------|
| X:  | \\\server\share\Marketing | ContosoMarketing |

它完全是為了確保使用者和群組具有，並維持適當的權限來存取檔案共用位置與內部部署檔案服務仍然可以存取您的責任。 此外，您應該儘速移除這類檔案共用的需求。

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>若要有對應的部署中 Microsoft 受管理電腦的磁碟機
 
請確定對應磁碟機無法避免使用，而且您提交任何服務要求之前先仔細檢閱需求。 然後遵循下列步驟：

1. 瀏覽至[Microsoft 受管理電腦入口網站](https://aka.ms/mmdportal)。  
2. 提交標題 」 對應磁碟機部署 「 為透過**支援 > 支援要求**] 區段中的支援要求，並提供所有必要的檔案共用的詳細資訊。  
3. Microsoft 受管理的桌上型電腦 IT 作業將會告知，藉由使用時，支援要求的更新，要求已完成。 最初將只部署此組態，測試部署群組中的裝置。  
4. 您必須測試並確認 Microsoft 受管理的桌上型電腦 IT 作業所部署的組態是否運作如預期般。 支援要求中使用 [討論] 索引標籤，以通知 Microsoft 受管理的桌上型電腦 IT 作業，當您完成測試的回覆。  
5. Microsoft 受管理的桌上型電腦 IT 作業小組會再將設定部署至其他部署群組。 
