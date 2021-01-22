---
title: '將 Google 檔案遷移到商務用 Microsoft 365 '
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解如何使用 Mover 將 Google 檔案遷移到商務用 Microsoft 365。
ms.openlocfilehash: 99040e4846aba084f40536e88f0aed70998f48be
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928195"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a>將 Google 檔案遷移到商務用 Microsoft 365 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

當您移轉商務用 Microsoft 365 時，會想要從 Google 雲端硬碟移轉檔案。 您可以使用 Mover 應用程式，從個人磁片磁碟機和共用磁片磁碟機移動檔案。 有關詳細資訊，請參閱 [Mover 雲端移移](https://docs.microsoft.com/sharepointmigration/mover-plan-migration)

> [!NOTE]
> Mover 會製作檔案的複本，並移至商務用 Microsoft 365。 原始檔案也會留在 Google 雲端硬碟中。

## <a name="before-you-start"></a>開始之前

所有使用者都應該已簽署商務用 Microsoft 365 並設定其商務用 OneDrive。 若要這麼做，請 [office.com](https://office.com)您的商務用 Microsft 365 認證進行登錄，然後選擇 [OneDrive。

## <a name="try-it"></a>試試看吧！

### <a name="install-mover"></a>安裝 Mover

1. 在 admin.google.com 上，[請admin.google.com。](https://admin.google.com)

1. 選擇 **應用程式** **、Google Workspace Marketplace 應用程式**，然後 **新增應用程式至網域安裝清單**。

1. 搜尋並選取 Mover。

1. 選擇 **網域安裝，** 然後 **繼續**。

1. 請審查許可權，選取核取方塊以同意條款，然後選取 **允許，選擇****下一** 步，然後 **完成**。

### <a name="create-connectors-and-run-the-migration"></a>建立連接器及執行移移

1. 返回 **Google Workspace Marketplace 應用程式**。
1. 重新更新瀏覽器，然後選取 **Mover** App。
1. 向下卷軸並選擇通用流覽連結。
1. 選取 **授權新連接器**，找到 **G Suite (系統管理員) ，****然後選擇授權。**
1. 您可以變更 **顯示名稱**，然後 **選取授權。**
1. 選擇 Google 系統管理帳戶、審查許可權， **然後選取允許**。

    Mover 會顯示所找到的團隊磁片磁碟機和使用者磁片磁碟機數量。 

1. 在 **選取目的地下**，選擇 **授權新連接器**，找出 **Office 365，****然後選取** 授權。
1. 若要將許可權授予您 Azure Active Directory 中的 Mover 應用程式，請 [流覽至](https://aka.ms/Office365MoverAuth)aka.ms/Office365MoverAuth。
1. 選取 **Office 365 Mover、****許可權、****為貴公司授予系統管理員同意**。
1. 選擇您的帳戶、審查許可權， **然後選取接受**。
1. 選擇 **屬性** ，並確認需要 **使用者指派？** 已開啟。
1. 回到 Mover App，視需要變更顯示名稱，選擇 **授權，然後** 選取 Microsoft 系統管理員帳戶。

    Mover 會告知您 SharePoint Online 使用者或 SPO (網站) 使用者數目。
1. 選擇 **繼續移移設定**，選取 **新增使用者，** 然後 **自動探索和新增使用者。**

    Mover App 會嘗試將雲端硬碟從 Google 的 Source Path，到 Microsoft 365 中的目的地路徑。 

    如果磁片磁碟機無法自動進行地圖，請將其目的地路徑新增到 CSV 檔案，我們會稍後再使用這個路徑，將共用磁片磁碟機遷移到 SharePoint 文件庫。 

1. 在此案例中，我們已新增名為移案的 SharePoint 網站，並記下檔頁面的 URL。 
1. 接著，我們使用來源路徑、目的地路徑和標記的格式來建立 CSV 檔案。 

    詳情[請參閱aka.ms/movercsv。](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv)

    新增目的地路徑 URL 時，請移除共用文件之後的所有專案，例如，這個完整的 URL 將無法執行： `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`

    將其變更為：`https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`

1. CSV 檔案準備就緒後，請選取移移動作 **、新增** 到移案、**選擇要上傳的檔案**。
1. 流覽至您的 CSV 檔案，選取該檔案，**然後選擇開啟。**
1. 選取您想要移移其檔案的使用者磁片磁碟機，然後選擇 **開始移移使用者。**
1. 請審查移移資訊，選擇何時開始移移，同意條款 **及條件**， **然後選取繼續**。

移移程式完成時，Mover App 會通知您。