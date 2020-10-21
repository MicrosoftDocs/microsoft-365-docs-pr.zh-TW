---
title: 手動變更商務用 Microsoft 365 方案
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- commerce
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ROBOTS: NOINDEX
description: 購買新的訂閱以手動變更訂閱，並確保訂閱同時列出並使用中。
ms.openlocfilehash: 09557b3556db1e6f17d7a4cd54a88ba34d0f0bd7
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48647816"
---
# <a name="change-plans-manually"></a>手動變更計畫

## <a name="step-1-decide-how-to-change-plans"></a>步驟1：決定變更方案的方式

若要將所有使用者從一個計畫變更為另一個計畫，最好的方法是 [使用 [升級]](upgrade-to-different-plan.md)索引標籤。有時候這是不可能的。 改為手動變更方案：

- [ **升級** ] 索引標籤表示您無法升級目前的計畫。

- 當您選取 [ **升級** ] 索引標籤時，您想要的計畫並未列出。

- 如果您不想以相同的方式升級所有使用者。 有些企業需要不同的使用者訂閱不同的方案。 使用此做的手動變更。

若要繼續進行手動變更，請參閱本主題中 [的步驟2：購買新的訂閱](#step-2-buy-a-new-subscription) 。

> [!IMPORTANT]
> 若要變更為與目前的計畫不同的資料相關服務所使用的計畫 (降級) ，您必須手動備份想要保留的任何資料。 如需詳細資訊，請參閱 [在變更計畫之前備份資料](back-up-data-before-switching-plans.md)。

## <a name="step-2-buy-a-new-subscription"></a>步驟2：購買新的訂閱

**已購買？** 如果您已有要將使用者移至其中的訂閱，請略過此步驟，然後移至 [ [步驟3：檢查您](#step-3-check-your-new-subscription-and-licenses) 在本主題中的新訂閱與授權]。

OR

**購買新的訂閱與授權：** 請遵循 [購買其他 Microsoft 365 for business 訂閱](../buy-another-subscription.md) 中的步驟，購買新的訂閱。

請確認您購買的是使用者現在所在組織的訂閱。 例如，檢查您要移動之使用者的電子郵件地址。 如果他們的電子郵件地址包括 \@ contoso.com，您必須購買 contoso.com 的新訂閱。
針對每個您想要移動的使用者，加入一個授權。

## <a name="step-3-check-your-new-subscription-and-licenses"></a>步驟3：檢查您的新訂閱與授權

1. 在系統管理中心，移至 **[帳單]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[您的產品]</a> 頁面。

2. **確認同時列出和使用中的兩個訂閱** 您要將使用者移至其中的訂閱，以及您要將使用者移至其中的訂閱，必須一起列出。 如果您第一次檢查時新的訂閱不在那裡，請稍後再試一次。 檢查這兩個訂閱是否都在使用中。 [未列出或未使用中的新訂閱](#the-new-subscription-isnt-listed-or-isnt-active)。

3. **檢查您是否有足夠的授權可供每個使用者使用** 每個使用者都需要符合其訂閱的授權。 因此，如果您想要將十位使用者移至 Microsoft 365 商務版 Premium，您必須確定有10個授權可供使用。

4. **新訂閱需要更多授權？**
   移至 [ **產品** ] 頁面並 [購買更多授權](../licenses/buy-licenses.md)。

> [舊的授權為何？](#what-about-the-old-licenses)

### <a name="the-new-subscription-isnt-listed-or-isnt-active"></a>未列出或未使用的新訂閱

- **如果您已購買兩個訂閱，而且不會同時列出**，則可能是針對不同的網域) ，購買不同組織 (。 訂閱無法跨組織界限。

- **如果您知道有其他訂閱**，且未在這裡列出，或未使用 active，請 [致電 Microsoft 支援人員](../../admin/contact-support-for-business-products.md)。

### <a name="what-about-the-old-licenses"></a>舊的授權為何？

將稍後移除目前訂閱的授權;您只需要支付新的使用者授權。

## <a name="step-4-reassign-licenses"></a>步驟4：重新指派授權

### <a name="reassign-a-license-for-one-user"></a>為一位使用者重新指派授權

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。

2. 在 [作用中 **使用者** ] 頁面上，選取您要指派授權的使用者。

3. 在 [ **授權和應用程式** ] 索引標籤上，展開 [ **授權**]，選取您要指派之授權的方塊，然後選取 [ **儲存變更**]。

### <a name="reassign-licenses-for-multiple-users-at-once"></a>一次為多位使用者重新指派授權

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。

2. 選取您要取代現有授權的使用者名稱旁的圓圈。

3. 在頂端，選取 [ **更多選項** (**...**) ]，然後選擇 [ **管理產品授權**]。

4. 選取 [ **取代現有的產品授權指派** \> **] [下一步]**。

5. 針對您想要指派給這些使用者的產品，將開關切換到 [ **開啟** ] 位置。

    > [!TIP]
    > - 若要限制使用者可使用的服務，請切換至 [ **關閉** ] 以切換至您要針對該使用者移除的服務。 例如，如果您想要使用者能夠存取所有可用的服務（商務用 Skype Online 除外），您可以將商務用 Skype Online 服務的切換切換到 [ **關閉** ] 位置。
    > - 將移除任何先前指派給所選使用者的授權。

6. 在 **[取代現有產品]** 窗格中，選取 **[取代]** \> **[關閉]**。

## <a name="step-5-cancel-subscriptions-or-remove-licenses-that-you-no-longer-need-optional"></a>步驟5：取消預訂或移除您不再需要的授權 (選用) 

如果您將所有使用者從一個訂閱移到另一個訂閱，且您不再需要原本的訂閱，可以[取消訂閱](cancel-your-subscription.md)。

如果您只將部分使用者移至不同的訂閱，請移除您不再需要的 [授權](../licenses/remove-licenses-from-subscription.md) 。

## <a name="call-support-to-help-you-change-plans"></a>通話支援以協助您變更方案
[撥打 Microsoft 支援服務](../../admin/contact-support-for-business-products.md)