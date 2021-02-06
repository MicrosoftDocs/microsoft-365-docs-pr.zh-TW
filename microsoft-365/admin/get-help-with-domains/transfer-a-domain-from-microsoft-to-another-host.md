---
title: 將網域從 Microsoft 轉接至其他主機
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
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: '在這裡尋找將網域從 Microsoft 轉接至另一個註冊機構的步驟。 '
ms.openlocfilehash: f34e9733ab53c8bdc6f4432c96e6232ecc26ee06
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126344"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a>將網域從 Microsoft 轉接至其他主機

您在從 Microsoft 購買網域之後，您無法將 Microsoft 365 網域轉接至另一個註冊機構60天。

> [!NOTE]
> _Whois_   查詢會顯示 Microsoft 購買的網域報名者做為通配網域 LLC。 不過，只應該與 microsoft 365 購買的網域聯繫。

請遵循下列步驟，取得 Microsoft 365 的程式碼，然後移至另一個網域註冊機構網站，設定將您的功能變數名稱轉移至新的註冊機構。

## <a name="transfer-a-domain"></a>傳輸網域

1. 在系統管理中心中，移至 [  **設定**] [   >  **網域**]。

2. 在 [ **網域** ] 頁面上，選取您要轉接至另一個網域註冊機構的 Microsoft 365 網域，然後選取 [ **檢查健康情況**]。

3. 在頁面頂端，選取 [ **轉移網域**]。

4. 在 [ **選擇要將您的網域轉接至何處** ] 頁面上，選取 **不同的註冊機構**，然後按 **[下一步]**。

5. 在 [**解除鎖定網域轉移**] 頁面上，選取 [ **<_您的網域_ > 解除鎖定傳輸**]，然後選取 **[下一步]**。

6. 請檢查您的網域轉接連絡人資訊，然後選取 **[下一步]**。

7. 在繼續進行下一個步驟之前，請複製授權碼，並等候大約30分鐘，讓您的網域傳送狀態變更為 [**註冊**] 索引標籤上的 [**轉移未鎖定**]。

8. 移至您想要管理功能變數名稱的網域註冊機構網站。 遵循傳送網域的指導 (搜尋以取得其網站的協助) 。 這通常表示支付轉接費用，並將 Authcode 給新的註冊機構，讓他們可以開始進行轉接。 Microsoft 會傳送電子郵件給您，以確認我們已接收到轉接要求，而且網域會在5天內轉接。

    您可以在 Microsoft 365 的 [ **網域**] 頁面上，找到 [授權碼 **註冊**] 索引標籤。
    
    > [!TIP]
    > uk 網域需要不同的程式。 請聯繫我們的 Microsoft 支援服務，要求 IPS 標籤 **變更** ，以符合您想要管理網域的註冊機構。 一旦標籤變更，網域就會立即傳輸至新的註冊機。 然後您必須與新的註冊機構合作，以完成傳送，很可能會支付轉接費用，並使用新的註冊機構將轉移的網域新增至您的帳戶。

9. 完成傳輸後，您將會在新的網域註冊機構中更新您的網域。

10. 若要完成此程式，請回到系統管理中心的 [ **網域** ] 頁面，然後選取 [  **完成網域傳輸**]。 這會將網域標示為不再從 Microsoft 365 購買，並且會停用網域訂閱。 它不會從承租人中移除網域，也不會影響網域上現有的使用者和信箱。

> [!NOTE]
> Microsoft 365 購買的網域不符合名稱伺服器的變更或在 Microsoft 365 組織之間傳輸網域的資格。 若有任何一種是必要的，網域註冊必須轉移到另一個註冊機構。
