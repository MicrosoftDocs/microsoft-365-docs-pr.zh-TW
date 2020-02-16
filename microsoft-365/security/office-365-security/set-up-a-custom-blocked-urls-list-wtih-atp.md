---
title: 使用 Office 365 ATP 安全連結來設定自訂封鎖的 Url 清單
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
ms.collection:
- M365-security-compliance
description: 了解如何使用 Office 365 進階威脅防護為貴組織設定封鎖的 URL 清單。 封鎖的 URL 會根據您的 ATP 安全連結原則，套用至電子郵件訊息和 Office 文件。
ms.openlocfilehash: 5205fbd5ccc873513eed4e367119084516e92bf2
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42088085"
---
# <a name="set-up-a-custom-blocked-urls-list-using-office-365-atp-safe-links"></a>使用 Office 365 ATP 安全連結來設定自訂封鎖的 Url 清單

> [!IMPORTANT]
> 本文適用於擁有 [Office 365 進階威脅防護](office-365-atp.md)的企業客戶。 如果您是家用版使用者且正在尋找 Outlook 中安全連結的相關資訊，請參閱[進階 Outlook.com 安全性](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2)。

使用 [Office 365 進階威脅防護 ](office-365-atp.md) (ATP)，貴組織即可擁有已封鎖的網站位址 (URL) 自訂清單。 當 URL 遭到封鎖時，按一下封鎖的 URL 連結人員會被帶到[警告頁面](atp-safe-links-warning-pages.md)，類似下列影像： 
  
![網站已遭封鎖](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
封鎖的 URL 清單是由貴組織的 Office 365 安全性小組所定義，而該清單適用於組織中受 Office 365 ATP 安全連結原則涵蓋的所有人員。 
  
請參閱此文章以了解如何為 [Office 365 中的 ATP 安全連結](atp-safe-links.md)設定貴組織的自訂封鎖 URL 清單。
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a>檢視或編輯自訂封鎖 URL 清單

[Office 365 中的 ATP 安全連結](atp-safe-links.md)使用多種清單，包含貴組織的自訂封鎖 URL 清單。 如果您具有必要權限，則可以設定貴組織的自訂清單。 您可以編輯貴組織的預設安全連結原則來執行此動作。

若要編輯 (或定義) ATP 原則，您必須獲指派為以下表格所述之其中一個角色： 

|角色  |指派位置/條件  |
|---------|---------|
|Office 365 全域系統管理員 |註冊購買 Office 365 的人會預設為為全域系統管理員。 (請參閱[關於 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)以深入了解。)         |
|安全性系統管理員 |Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online 組織管理 |Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>或 <br>  PowerShell Cmdlet (請參閱 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)) |

> [!TIP]
> 若要深入了解角色和權限，請參閱 [Office 365 安全性的權限 &amp; 合規性中心](permissions-in-the-security-and-compliance-center.md) (英文)。

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a>若要檢視或編輯自訂封鎖 URL 清單
  
1. 移至 [https://protection.office.com](https://protection.office.com) 然後以您的公司或學校帳戶當入。 
    
2. 在左側瀏覽中，選擇 [威脅管理] **** 下方的 [原則] ****\>[安全連結]****。
    
3. 在 **套用於整個組織的原則**區段中，選取 [預設] ****，然後選擇 [編輯] **** (編輯按鈕類似鉛筆)。<br/>![按一下 [編輯] 已編輯安全連結防護預設原則](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)<br/>這樣做可讓您檢視封鎖的 URL 清單。 一開始您可能沒有任何列出的 URL。<br/>![預設安全連結原則中封鎖的 URL 清單](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)
  
4. 選取 [輸入有效的 URL] 方塊****，輸入 URL，然後選擇加號 (**+**)。 

5. 完成新增 URL 之後，在螢幕畫面右下角選擇 [儲存] ****。
    
## <a name="a-few-things-to-keep-in-mind"></a>謹記幾件事項

新增 URL 至清單時，請記住下列要點： 

- 請勿在 URL 結尾包含斜線 (**/**)。 例如，輸入 `https://www.contoso.com`，而不是輸入 `https://www.contoso.com/`。
    
- 您可以指定的只有網域的 URL (像是 `contoso.com` 或 `tailspintoys.com`)。 這會封鎖任何含有網域的 URL 點擊。

- 您可以指定子網域 (像是 `toys.contoso.com*`) 而不封鎖完整網域 (像是 `contoso.com`)。 這將會封鎖含有子網域的任何 URL 點擊，但不會封鎖點擊含有完整網域的 URL。  
    
- 每個 URL 最多可以包含三個萬用字元星號 (\*)。 下表列出您可以輸入的內容範例，以及這些項目的影響。
    
|**範例項目**|**功能**|
|:-----|:-----|
|`contoso.com` 或 `*contoso.com*`  <br/> |封鎖網域、子網域和路徑，例如 `https://www.contoso.com`、`https://sub.contoso.com` 和 `https://contoso.com/abc`  <br/> |
|`https://contoso.com/a`  <br/> |會封鎖網站 `https://contoso.com/a`，但不會封鎖其他子路徑，像是 `https://contoso.com/a/b`  <br/> |
|`https://contoso.com/a*`  <br/> |會封鎖網站 `https://contoso.com/a`和其他子路徑，像是 `https://contoso.com/a/b`  <br/> |
|`https://toys.contoso.com*`  <br/> |封鎖子網域 (在這個例子中為「玩具」)，但允許按一下其他網域 URL (像是 `https://contoso.com` 或 `https://home.contoso.com`)。  <br/> |
   

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a>如何定義組織中特定使用者的例外情況

如果您希望特定群組能夠檢視其他人可能封鎖的 URL，您可以指定可套用至特定收件者的 ATP 安全連結原則。 請參閱[使用 ATP 安全連結設定自訂「不可覆寫」URL 清單](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) (英文)。
  

