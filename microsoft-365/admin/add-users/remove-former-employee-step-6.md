---
title: 步驟 6-移除並刪除離職員工的 Microsoft 365 授權
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 請遵循下列步驟，從離職員工移除 Microsoft 365 授權。
ms.openlocfilehash: ed86eb28cc6d4996f7def8cb567f0e4085e67624
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244163"
---
# <a name="step-6---remove-the-microsoft-365-license-from-a-former-employee"></a>步驟 6-移除來自離職員工的 Microsoft 365 授權

如果您不想要在某人離開組織之後支付授權，您必須移除其 Microsoft 365 授權，然後將其從您的訂閱中刪除。 若未刪除，您可以將授權指派給其他使用者。
  
在移除授權之後，該使用者的所有資料會保留 30 天。 您可以[存取](get-access-to-and-back-up-a-former-user-s-data.md)資料，或者如果該使用者復職，也可以[還原](restore-user.md)帳戶。 30天后，除了 SharePoint 線上) 上儲存的檔之外，所有使用者的資料 (，都將從 Microsoft 365 中永久刪除，且無法復原。

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。
2. 選取您要封鎖的員工名稱，然後選取 [ **授權與應用程式** ] 索引標籤。
3. 清除您要移除之授權 () 的核取方塊，然後選取 [ **儲存變更**]。

**若要減少** 您在雇用另一個人之前所支付的授權數量，請執行下列步驟：

1. 在系統管理中心中，移至 [ **帳單** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">產品</a> ] 頁面，然後選取 [ **產品** ] 索引標籤。
2. 選取您要移除授權的訂閱。
3. 在 [詳細資料] 頁面上，選取 [ **移除授權**]。
4. 在 [ **移除授權** ] 窗格中的 [新數量] 底下的 [ **授權總數** ] 方塊中，輸入此訂閱所需的授權總數。 例如，如果您有25個授權，而您想要移除其中一個，請輸入24。
5. 選取 ****[儲存]。

當您在公司中 [新增其他人員](add-users.md) 時，系統會同時提示您購買授權，只須一個步驟！

如需管理 Microsoft 365 商務用的使用者授權的詳細資訊，請參閱[在商務用 Microsoft 365 中指派授權給使用者](../manage/assign-licenses-to-users.md)，並為[商務用 Microsoft 365 中的使用者取消指派授權](../manage/remove-licenses-from-users.md)。
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a>已刪除的員工的帳戶會如何影響商務用 Skype

當您在 Office 365 中移除使用者的授權後，系統會釋出與該使用者相關的 PSTN 通話號碼，方便您將該號碼指派給其他使用者。
  
如果授權被移除的使用者屬於某個佇列群組，通話佇列代理程式將無法再指定這些使用者。因此，我們建議您一併從與該通話佇列相關的群組中移除該使用者。

## <a name="set-up-call-forwarding-to-people-in-your-organization"></a>設定對組織中人員的來電轉接

如果您需要設定終止員工之電話號碼的來電轉接，[呼叫原則] 底下的「來電轉接」設定可以設定轉寄，讓來電可以轉寄給其他使用者或同時撥打另一位人員。 如需詳細資訊，請參閱[在 Microsoft Teams 中通話原則](/microsoftteams/teams-calling-policy)。
