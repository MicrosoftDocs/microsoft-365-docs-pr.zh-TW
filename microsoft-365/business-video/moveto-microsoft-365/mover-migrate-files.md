---
title: '將 Google 檔案遷移至適用于 business 的 Microsoft 365 '
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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解如何使用移動器將 Google 檔案遷移至 Microsoft 365 供商務使用。
ms.openlocfilehash: 6feabff7e36e84f7dba56e74333648325cf43920
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913571"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a>將 Google 檔案遷移至適用于 business 的 Microsoft 365 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

當您移至 Microsoft 365 供商務用時，您會想要從 Google 雲端硬碟遷移檔案。 您可以使用移動器應用程式，從個人和共用磁片磁碟機移動檔案。 如需詳細資訊，請參閱 [移動雲端遷移](/sharepointmigration/mover-plan-migration)。

> [!NOTE]
> 移動器會製作檔案複本，並將複本移至 Microsoft 365 供商務使用。 原始檔案也會保留在 Google 磁片磁碟機中。

## <a name="before-you-start"></a>開始之前

所有使用者都應該登入 Microsoft 365 以供商務用，並設定其商務用 OneDrive。 若要這麼做，請移至[office.com](https://office.com)，使用您的商務用 Microsoft 365 來登入，然後選擇 [OneDrive]。

## <a name="try-it"></a>試試看吧！

### <a name="install-mover"></a>安裝移動器

1. 在 [admin.google.com](https://admin.google.com)登入 Google Workspace 管理主控台。

1. 選擇 [**應用** 程式  >  **Google Workspace Marketplace 應用** 程式  >  **將應用程式新增至網域安裝] 清單**。

1. 搜尋移動器並選取它。

1. 選擇 [ **網域安裝**]，然後 **繼續**。

1. 檢查許可權，選取 [同意] 核取方塊，然後選取 [ **允許**]，再選擇 **[下一步]**，然後 **執行**。

### <a name="create-connectors-and-run-the-migration"></a>建立連接器並執行遷移

1. 回到 **Google Workspace Marketplace 應用程式**。
1. 重新整理瀏覽器，然後選取 **移動** 器應用程式。
1. 向左下向，然後選擇通用導覽連結。
1. 選取 [ **授權新的連接器**]，找出 [ **G Suite (管理)**]，然後選擇 [ **授權**]。
1. 如有需要，請變更 **顯示名稱**，然後選取 [ **授權**]。
1. 選擇 Google 系統管理員帳戶，複查許可權，然後選取 [ **允許**]。

    移動器顯示所探索的團隊磁片磁碟機和使用者磁片數目。 

1. 在 [**選取目的地**] 底下，選擇 [**授權新的連接器**]，找出 **Office 365**，然後選取 [**授權**]。
1. 若要將許可權授與 Azure Active Directory 中的移動器應用程式，請流覽至[aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth)。
1. 選取 [ **Office 365 移動器**]**許可權**，**授與您公司的系統管理員同意**。
1. 選擇您的帳戶，查看許可權，然後選取 [ **接受**]。
1. 選擇 [ **屬性** ]，然後確認 [ **需要使用者指派]？** 已開啟。
1. 回到移動器應用程式，變更 **顯示名稱**（如有需要），選擇 [ **授權**]，然後選取 Microsoft 系統管理員帳戶。

    行動電話會通知您 SharePoint 線上 (或 SPO) 網站與所探索的使用者數目。
1. 選擇 [ **繼續遷移設定**]，選取 [ **新增使用者**]，然後 **自動探索及新增使用者**。

    移動器應用程式會嘗試將 Google 中來源路徑的磁片磁碟機，對應至 Microsoft 365 中的目的地路徑。 

    如果磁片磁碟機未自動對應，請將其目的地路徑新增至 CSV 檔案，我們稍後將用來將共用磁片磁碟機遷移至 SharePoint 文件庫。 

1. 在此情況下，我們已新增稱為「遷移檔案」的 SharePoint 網站，並記下 [檔] 頁面的 URL。 
1. 然後，我們會使用來源路徑、目的地路徑及標記的格式建立 CSV 檔案。 

    如需詳細資訊，請參閱 [aka.ms/movercsv](/sharepointmigration/mover-create-migration-csv)。

    新增目的地路徑 URL 時，請移除共用檔之後的所有專案。 例如，以下完整的 URL 將無法運作：`https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`

    將其變更為：`https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`

1. 當您的 CSV 檔案準備好後，請選取 [ **遷移動作**] [ **新增至遷移**]，然後 **選擇要上傳的** 檔案。
1. 流覽至您的 CSV 檔案，選取它，然後選擇 [ **開啟**]。
1. 選取您要遷移其檔案的使用者磁片磁碟機，然後選擇 [ **開始遷移使用者**]。
1. 檢查遷移資訊，選擇何時開始遷移，請同意 **條款及條件**，然後選取 [ **繼續**]。

移動器應用程式會在遷移過程完成時通知您。