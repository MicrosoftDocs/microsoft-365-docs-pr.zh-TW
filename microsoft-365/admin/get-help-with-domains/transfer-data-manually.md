---
title: 兩個 Office 365 帳戶之間手動傳送資料
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
- MOE150
ms.assetid: 7dc5d983-84b2-4802-bef0-602ae1780a42
description: 尋找如何在兩個 Office 365 帳戶時變更計劃] 或 [公司名稱，或結合成一個多個訂閱之間手動傳送資料。
ms.openlocfilehash: 91f9d7b17a0296931393a89ff95d70628400c61a
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2020
ms.locfileid: "42362148"
---
# <a name="transfer-data-manually-between-two-office-365-accounts"></a>兩個 Office 365 帳戶之間手動傳送資料

準備袖子及封鎖時間行事曆中的一串： 兩個 Office 365 帳戶之間傳輸資料是手動、 複雜，且耗時的程序。 這不是自動化或支援處理程序。 我們將協助您開始。
  
> [!CAUTION]
> 將會有停機時間期間，將不會在電子郵件、 商務用 Skype 和裝載於 Office 365 公用網站的程序。 使用者會收到新的使用者名稱和密碼，以及他們將需要設定 Outlook 重設。

**僅限傳輸資料以手動方式使用下列其中一項適用於本主題中的指示：**
  
- 您要變更為不同的服務系列中的計劃。

- 您的公司名稱變更，而您決定建立新的訂閱，然後移轉您的資料，因為您想要使用不同的初始網域名稱。

- 您必須合併到一個新的多個訂閱。

> [!IMPORTANT]
> 如果您需要[變更您訂閱計劃](../../commerce/subscriptions/switch-to-a-different-plan.md)，並可以使用切換方案精靈，或如果您需要移轉至新訂閱計劃在相同的訂閱系列，即使切換方案精靈無法運作，您不需要以手動方式傳送您的資料，且沒有任何停機時間。

|**Tasks**|**Steps**|
|:-----|:-----|
|購買您想要將移至的計劃。  <br/> |當您註冊時，您會指定要使用的初始網域名稱中的公司名稱： *yourcompany* 。 onmicrosoft.com、 *yourcompany* -public.sharepoint.com 和*yourcompany* 。 sharepoint.com。 您需要使用不同的*yourcompany*名稱比您沒有任何現有的訂閱。  <br/> > [!NOTE]它通常採用之後取消訂閱發行的初始網域名稱，使用*yourcompany*從我們系統的幾個月內至少要有 # C0。 即使您計劃以儲存您的所有資料從您舊的 Office 365 訂閱，並取消該訂閱，舊的*yourcompany*值不是立即適用於新訂閱。           |
|從舊的 Office 365 訂閱中移除您的自訂網域。  <br/> | 請依照下列[所需的步驟，然後再移除網域](remove-a-domain.md)來移除使用者電子郵件地址的網域名稱，並移除電子郵件的 DNS 記錄和 Lync for 自訂的網域。 如果您裝載於 Office 365 公用網站，您也需要移除指向它的 CNAME 記錄。  <br/> > [!IMPORTANT]> 之後移除路由電子郵件到這個自訂的網域、 電子郵件，將會停止工作，直到您新增網域至您的新帳戶，MX 記錄設定新的 MX 記錄，並設定您的使用者。 當您移除的 DNS 記錄 lync 時，Lync 會停止運作。 與您移除的 CNAME 記錄，指向您的公用網站之後，它將無法使用。           [移除網域](remove-a-domain.md)。  <br/> |
|設定自訂網域用於新訂閱，並設定您的使用者。  <br/> | 設定新訂閱，包括建立必要的 DNS 記錄的自訂網域。  <br/>  建立您的使用者，您的自訂網域的電子郵件地址。  <br/> |
|將資料從您的舊訂閱傳輸至新訂閱。  <br/> | 登入這兩個不同的瀏覽器視窗中的帳戶：  <br/>  以滑鼠右鍵按一下 [Internet Explorer] 圖示，並開啟兩個 InPrivate 瀏覽器視窗。 您可以使用兩個視窗中的不同的認證來登入這兩個帳戶。  <br/> [訂閱之間傳送的系統管理設定](#email) <br/> [小組網站結構與資料傳輸](#transfer-team-site-structure-and-data) <br/> [訂閱之間傳送的公用網站](#transfer-a-public-website-between-subscriptions) <br/> [訂閱之間傳送的系統管理設定](#email) <br/> |
|您必須取消訂閱大功告成與藉由呼叫 Microsoft 支援服務運作的 Office 365 計劃。  <br/> | 確認您的新訂閱正常運作，且已傳送的所有資料。  <br/>  取消舊訂閱請[連絡客戶支援](../contact-support-for-business-products.md)。  <br/> |

## <a name="transfer-administrative-settings-between-subscriptions"></a>訂閱之間傳送的系統管理設定

移至下列頁面上每個帳戶，and set up 舊的帳戶設定為基礎的新帳戶。
  
如果您傳送的資料從 Office 365 Office 365 中型企業版或 Office 365 企業版，會以不同方式結構化的系統管理頁面。 監看[影片： 介紹 Office 365 企業版](https://support.office.com/article/11f7b4a0-1294-4e94-9238-beaae26efa9c.aspx)，並移至下列位置，查看 [系統設定。
  
Office 365 企業版和 Office 365 中型企業版：
  
|**位置**|**用途**|
|:-----|:-----|
|**系統管理員** \> **Office 365** \> **服務設定** <br/> |選取郵件、 網站、 Lync、 使用者軟體、 密碼、 社群、 版權管理和行動裝置設定每個索引標籤。  <br/> |
|**系統管理員** \> **Exchange** <br/> | Exchange Online 設定  <br/> |
|**系統管理員** \> **SharePoint** <br/> | SharePoint Online 設定  <br/> |
|**系統管理員** \> **商務用 Skype** <br/> |業務設定其他商務用 Skype  <br/> |

適用於 Office 365 小型企業
  
|**位置**|**用途**|
|:-----|:-----|
|**系統管理員** \> **管理整個組織的設定** <br/> |系統管理設定  <br/> |

## <a name="transfer-a-public-website-between-subscriptions"></a>訂閱之間傳送的公用網站

如果您有裝載於 Office 365 公用網站，您需要將它儲存及重新建立新的訂閱。
  
> [!NOTE]
> 如果您的公用網站架設在 DNS 主機服務提供者，不不需要任何變更。 它將不會受到轉換。
  
若要從 SharePoint Online 環境儲存文件庫或清單內容的檔案共用或本機電腦，請參閱[手動移轉的 SharePoint Online 的內容](https://go.microsoft.com/fwlink/p/?LinkId=402910)。
  
> [!NOTE]
> 公用網站移轉應用程式不能將資料傳送至不同的訂閱。
  
## <a name="transfer-team-site-structure-and-data"></a>小組網站結構與資料傳輸

有幾種方式可以儲存資料或傳輸小組網站：
  
- 您可以儲存舊網站為範本，並將此範本匯入新的網站。

- 若要傳輸文件，先手動重新建立您階層，新的網站。 然後您可以同時開啟這兩個 SharePoint 小組網站、 使用 Windows 檔案總管] 中，開啟這兩個文件庫和複製並貼文件。 請參閱[影片： 複製或移動文件庫檔案使用檔案總管中開啟](https://support.office.com/article/c27bc6f3-7b38-4c29-b947-5d00c7153384.aspx)。

- 若要傳輸清單資料，將[清單範本](https://support.office.com/article/c3884ad1-bc49-44b8-b3d6-3bc6a01eb393.aspx)，儲存並使用儲存的範本重新建立新的網站上的清單。

- 若要儲存文件庫或清單內容從 SharePoint Online 環境 (商務用 OneDrive 或小組網站)，檔案共用或本機電腦，請參閱[手動移轉的 SharePoint Online 內容的相關資訊](https://support.microsoft.com/kb/2783484)。

## <a name="transfer-users-data-between-subscriptions"></a>訂閱之間傳送使用者的資料

### <a name="email"></a>電子郵件：

設定新訂閱之後，請要求使用者將[移動他們的電子郵件、 連絡人、 工作和行事曆資訊](https://support.office.com/article/0996ece3-57c6-49bc-977b-0d1892e2aacc.aspx)。 他們可以使用其初始的使用者名稱，例如 sue@contoso.onmicrosoft.com 取得其舊的電子郵件。
  
### <a name="onedrive-for-business-data"></a>商務用 OneDrive 的資料：

要求使用者在複製/同步處理[商務用 OneDrive 內容至其電腦](https://support.office.com/article/59b1de2b-519e-4d3a-8f45-51647cf291cd.aspx)，並再將其新增至其新的訂閱。
