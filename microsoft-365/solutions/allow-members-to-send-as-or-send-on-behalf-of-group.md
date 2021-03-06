---
title: 允許成員傳送為或代表群組傳送
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
recommendations: false
description: 瞭解如何允許群組成員以 Microsoft 365 群組的身分傳送電子郵件，或代表 Microsoft 365 群組傳送電子郵件。
ms.openlocfilehash: 437040700361c6a09b107a87d8228d2a156375d1
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926136"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a>允許成員傳送為或代表群組傳送

已授與「**代理傳送**」或「**代理傳送** 者」許可權的 Microsoft 365 群組成員可以傳送電子郵件給群組，或代表群組傳送電子郵件。 無法將許可權授與群組中的 (訪客。 ) 

本文說明全域管理員或 Exchange 管理員可如何設定這些許可權。
  
例如，如果 Megan Bowen 是 **訓練** Microsoft 365 群組的一部分，且具有群組的 [以該群組 **傳送**] 許可權，則當她傳送電子郵件做為群組時，它看起來就像是 **訓練** 群組傳送電子郵件。 
  
「**代理傳送** 者」許可權可讓使用者代表 Microsoft 365 群組傳送電子郵件。 例如，如果 Alex Wilber 是「**行銷** Microsoft 365 群組的一部分，且具有「**代理傳送** 者」許可權，並傳送電子郵件做為群組，則電子郵件看起來就像是由 **Alex Wilber 代表 Marketing** 所傳送。

> [!IMPORTANT]
> 您可以為特定使用者設定「 **傳送為** 」或「 **傳送代理** 」，但不能同時為這兩者。 如果您同時設定兩者，則預設會 **傳送為**。

> [!TIP]
> 請參閱[代表 Microsoft 365 群組傳送電子郵件](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)，以瞭解如何使用網頁上的 Outlook 和 Outlook 從群組傳送電子郵件。
    
## <a name="allow-members-to-send-email-as-a-group"></a>允許成員以群組形式傳送電子郵件

本節說明如何允許使用者以[Exchange 系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=2059104)的群組 (EAC) Exchange Online 中傳送電子郵件。
  
1. 在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 系統管理中心</a>，**移至 [** 收件者 \> **群組**]。
    
2. 在 ![ ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 您要允許使用者傳送的群組上，選取 [編輯編輯群組圖示]。   
    
3. 選取 [ **群組委派**]。
    
4. 在 [ **傳送方式** ] 區段中，選取要 **+** 新增為群組傳送之使用者的符號。 
    
    ![[傳送為] 對話方塊的螢幕擷取畫面](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. 若要從清單中搜尋或挑選使用者的類型。 選取 **[確定]** 並 **儲存**。
    
    ![在清單中搜尋或挑選使用者的類型](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a>允許成員代表群組傳送電子郵件

本節說明如何允許使用者代表 Exchange 系統管理中心的群組 (EAC) Exchange Online 中的群組傳送電子郵件。
  
1. 在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 系統管理中心</a>，**移至 [** 收件者 \> **群組**]。
    
2. 在 ![ ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 您要允許使用者傳送的群組上，選取 [編輯編輯群組圖示]。 
    
3. 選取 [ **群組委派**]。
    
4. 在 [代理傳送者] 區段中，選取要 **+** 新增為群組傳送之使用者的符號。 
    
    ![[代理傳送者] 對話方塊的螢幕擷取畫面](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. 若要從清單中搜尋或挑選使用者的類型。 選取 **[確定]** 並 **儲存**。
    
    ![在清單中搜尋或挑選使用者的類型](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a>相關文章

[共同作業管理規劃逐步](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[建立共同作業管理計畫](collaboration-governance-first.md)

[深入瞭解 Microsoft 365 群組](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission)

[Set-UnifiedGroup](/powershell/module/exchange/set-unifiedgroup)