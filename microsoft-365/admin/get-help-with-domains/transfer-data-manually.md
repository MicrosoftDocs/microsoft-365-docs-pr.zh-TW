---
title: 在兩個帳戶間手動傳輸資料
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 7dc5d983-84b2-4802-bef0-602ae1780a42
description: 尋找當您變更計畫或公司名稱時，如何在兩部 Microsoft 365 帳戶之間手動傳輸資料，或將多個訂閱組合為一個。
ms.openlocfilehash: 9916da50f4589f949d35466ca6aa8f1d79cc40ea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915503"
---
# <a name="transfer-data-manually-between-two-accounts"></a>在兩個帳戶間手動傳輸資料

準備逐步 sleeves，並在行事曆中封鎖時間區塊：在兩個 Microsoft 365 帳戶之間傳輸資料是手動、複雜且耗時的處理常式。 這不是自動化或支援的處理常式。 我們將開始著手。
  
> [!CAUTION]
> 在處理電子郵件、商務用 Skype 和主控于 Microsoft 365 的公用網站時，會發生停機時間。 使用者將會收到新的使用者名稱和密碼，並將需要重設 Outlook。

**若有下列其中一項適用，請僅使用本主題中的指示手動傳送資料：**
  
- 您必須變更為不同服務系列中的計畫。

- 您的公司名稱已變更，您決定建立新的訂閱並遷移您的資料，因為您想要使用不同的初始功能變數名稱。

- 您需要將多個訂閱合併成一個新的訂閱。

> [!IMPORTANT]
> 如果您需要 [變更您的訂閱計畫](../../commerce/subscriptions/switch-to-a-different-plan.md) ，而且可以使用 [切換方案] 嚮導; 或者，如果您需要在相同訂閱系列中轉移至新的訂閱計畫，即使 [切換方案] 嚮導無法運作，您不需要手動傳輸資料，也沒有停機時間。

|**Tasks**|**Steps**|
|:-----|:-----|
|購買您想要移至的計畫。  <br/> |當您註冊時，您可以指定要在初始功能變數名稱中使用的公司名稱：  *yourcompany*  onmicrosoft.com、  *yourcompany*  -public.sharepoint.com 及  *yourcompany*  。 您需要使用與任何現有訂閱相同的  *yourcompany*  名稱。  <br/> > [!NOTE]> 取消訂閱以發行從我們系統中使用  *yourcompany*  的初始功能變數名稱後，一般至少需要數個月。 即使您計畫將所有資料儲存在舊的 Microsoft 365 訂閱中，並取消該訂閱，舊的  *yourcompany*  值不會立即可用於新的訂閱。           |
|從舊的 Microsoft 365 訂閱中移除您的自訂網域。  <br/> | 在 [您移除網域](remove-a-domain.md) 以從使用者電子郵件地址中移除功能變數名稱和移除自訂網域的電子郵件和 LYNC 的 DNS 記錄之前，請遵循必要的步驟。 如果您在 Microsoft 365 上主控公用網站，您也需要移除指向該網站的 CNAME 記錄。  <br/> > [!IMPORTANT]> 在您移除將電子郵件路由傳送至此自訂網域的 MX 記錄後，電子郵件將停止運作，直到您將網域新增至您的新帳戶、設定新的 MX 記錄，並設定您的使用者。 當您移除 Lync 的 DNS 記錄時，Lync 將停止運作。 移除指向您公用網站的 CNAME 記錄之後，將無法使用此記錄。           [移除網域](remove-a-domain.md) 。  <br/> |
|為您的新訂閱設定您的自訂網域，並設定您的使用者。  <br/> | 設定您的新訂閱，包括為您的自訂網域建立所需的 DNS 記錄。  <br/>  建立您的使用者，並在自訂網域上使用電子郵件地址。  <br/> |
|將舊訂閱中的資料傳送至新的訂閱。  <br/> | 在不同的瀏覽器視窗中登入這兩個帳戶：  <br/>  以滑鼠右鍵按一下瀏覽器圖示，然後開啟兩個私人瀏覽器視窗。 您可以在兩個 windows 中使用不同的認證來登入這兩個帳戶。  <br/> [在訂閱間傳輸系統管理設定](#email) <br/> [傳輸小組網站結構和資料](#transfer-team-site-structure-and-data) <br/> [在訂閱間傳輸公用網站](#transfer-a-public-website-between-subscriptions) <br/> [在訂閱間傳輸系統管理設定](#email) <br/> |
|呼叫 Microsoft Support for Microsoft 365，以取消所做計畫的訂閱。  <br/> | 請確認您的新訂閱是否正常運作，且所有資料都已傳輸。  <br/>  [請與客戶支援部門聯繫](../contact-support-for-business-products.md) 以取消舊的訂閱。  <br/> |

## <a name="transfer-administrative-settings-between-subscriptions"></a>在訂閱間傳輸系統管理設定

移至每個帳戶的下列頁面，並根據舊帳戶的設定，設定新帳戶。
  
如果您要將資料從 Microsoft 365 轉接至 Microsoft 365 中型企業或 Microsoft 365 企業版，系統管理員頁面會以不同的方式結構化。 觀賞 [影片：介紹 Microsoft 365 Enterprise](../index.yml)，然後移至下列位置，以查看系統管理設定。
  
Microsoft 365 企業版和 Microsoft 365 中型企業版：
  
|**位置**|**用途**|
|:-----|:-----|
|系統 **管理員** \>**Microsoft 365** \>**服務設定** <br/> |選取每個索引標籤，以查看郵件、網站、Lync、使用者軟體、密碼、群組、版權管理及行動裝置的設定。  <br/> |
|系統 **管理員** \>**Exchange** <br/> | Exchange Online 設定  <br/> |
|系統 **管理員** \>**SharePoint** <br/> | SharePoint 線上設定  <br/> |
|系統 **管理員** \>**商務用 Skype** <br/> |其他商務用 Skype 設定  <br/> |

適用于 Microsoft 365 Small Business
  
|**位置**|**用途**|
|:-----|:-----|
|系統 **管理員** \>**管理整個組織的設定** <br/> |管理設定  <br/> |

## <a name="transfer-a-public-website-between-subscriptions"></a>在訂閱間傳輸公用網站

如果您的公用網站主控于 Microsoft 365，您必須加以儲存，並在新的訂閱上重新建立。
  
> [!NOTE]
> 如果您的公用網站主控于 DNS 主機服務提供者，則不需要進行任何變更。 您的轉換不會影響此方式。
  
若要將文件庫或清單內容從 SharePoint 線上環境儲存至檔案共用或本機電腦，請參閱 [手動遷移 SharePoint 線上內容](/sharepoint/troubleshoot/migration-tool/content-manual-migration)。
  
> [!NOTE]
> 公用網站遷移應用程式無法將資料傳輸至不同的訂閱。
  
## <a name="transfer-team-site-structure-and-data"></a>傳輸小組網站結構和資料

有幾種方式可以儲存或轉接小組網站資料：
  
- 您可以將舊網站儲存為範本，然後將範本匯入新的網站。

- 若要傳輸檔，請先在新網站上手動重新建立階層。 然後，您可以同時開啟這兩個 SharePoint 小組網站、使用 Windows Explorer 開啟文件庫，以及複製及貼上檔。 請參閱 [影片：使用 [以瀏覽器開啟] 複製或移動文件庫](https://support.microsoft.com/office/c7c20284-bc94-47f4-9728-d28e9daf0790)檔案。

- 若要傳輸清單資料、儲存 [清單範本](https://support.microsoft.com/office/c3884ad1-bc49-44b8-b3d6-3bc6a01eb393)，然後使用儲存的範本在新網站上重新建立清單。

- 若要從 SharePoint 線上環境儲存文件庫或清單內容 (OneDrive 為商務或小組網站) 至檔案共用或本機電腦，請參閱 [SharePoint 線上內容之手動遷移的相關資訊](https://support.microsoft.com/kb/2783484)。

## <a name="transfer-users-data-between-subscriptions"></a>在訂閱間傳輸使用者資料

### <a name="email"></a>電子郵件：

在您設定新訂閱後，請使用者 [移動電子郵件、連絡人、工作及行事曆資訊](https://support.microsoft.com/office/0996ece3-57c6-49bc-977b-0d1892e2aacc) 。 他們可以使用初始的使用者名稱（例如 sue@contoso.onmicrosoft.com）來取得舊的電子郵件。
  
### <a name="onedrive-for-business-data"></a>商務資料的 OneDrive：

要求使用者將 [商務內容的 OneDrive](https://support.microsoft.com/office/59b1de2b-519e-4d3a-8f45-51647cf291cd)複製/同步處理至其電腦，然後將其新增回其新訂閱。

### <a name="onenote"></a>OneNote 

要求使用者 [備份 OneNote](https://support.microsoft.com/office/back-up-notes-f58b34b0-611d-435e-87fa-7942a1767af4?ui=en-us&rs=en-us&ad=us) ，並將 [Notes 從備份還原](https://support.microsoft.com/en-us/office/restore-notes-from-a-backup-5daf9cb0-6769-4998-a5de-f044fdd0d831?ui=en-us&rs=en-us&ad=us) 至新的訂閱。