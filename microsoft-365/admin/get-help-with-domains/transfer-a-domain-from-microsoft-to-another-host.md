---
title: 將網域從 Microsoft 轉接至其他主機
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
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: '在這裡尋找將網域從 Microsoft 轉接至另一個註冊機構的步驟。 '
ms.openlocfilehash: 7e00f5ae2c36a06803a3f7a8acd825dcab90805c
ms.sourcegitcommit: 6fb2a1c404ea3c3573b0f7803bf17459a9387891
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788975"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a>將網域從 Microsoft 轉接至其他主機

您在從 Microsoft 購買網域之後，您無法將 Microsoft 365 網域轉接至另一個註冊機構60天。

> [!NOTE]
> _Whois_   查詢會顯示 Microsoft 購買的網域報名者做為通配網域 LLC。 不過，只應該與 microsoft 365 購買的網域聯繫。

請遵循下列步驟，取得 Microsoft 365 的程式碼，然後移至另一個網域註冊機構網站，設定將您的功能變數名稱轉移至新的註冊機構。

## <a name="transfer-a-domain"></a>傳輸網域

1. 在系統管理中心中，移至 [  **設定**] [   >  **網域**]。

2. <在 [ **網域** ] 頁面上，選取您要轉接至另一個網域註冊機構的 Microsoft 365 網域，然後選取 [ **檢查健康情況**]。

3. 在頁面頂端，選取 [ **轉移網域**]。

4. 在 [ **選擇要將您的網域轉接至何處** ] 頁面上，選取 **不同的註冊機構**，然後按 **[下一步]**。

5. 在 [**解除鎖定網域轉移**] 頁面上，選取 [ **<_您的網域_ > 解除鎖定傳輸**]，然後選取 **[下一步]**。

6. 請檢查您的網域轉接連絡人資訊，然後選取 **[下一步]**。

7. 在繼續進行下一個步驟之前，請複製授權碼，並等候大約30分鐘，讓您的網域傳送狀態變更為 [**註冊**] 索引標籤上的 [**轉移未鎖定**]。

8. 移至您想要管理功能變數名稱的網域註冊機構網站。 遵循傳送網域的指導 (搜尋以取得其網站的協助) 。

您可以在 Microsoft 365 的 [ **網域**] 頁面上，找到 [授權碼**註冊**] 索引標籤。

9. 完成傳輸後，您將會在新的網域註冊機構中更新您的網域。

10. 若要完成此程式，請回到系統管理中心的 [ **網域** ] 頁面，然後選取 [  **完成網域傳輸**]。

> [!NOTE]
> Microsoft 365 購買的網域不符合名稱伺服器的變更或在 Microsoft 365 組織之間傳輸網域的資格。 若有任何一種是必要的，網域註冊必須轉移到另一個註冊機構。
